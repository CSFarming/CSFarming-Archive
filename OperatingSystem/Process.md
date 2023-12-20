## 1. 프로세스
- 운영체제로부터 자원을 할당받은 작업의 단위
- 컴퓨터에서 실행 중인 프로그램을 의미
- 프로그램(Program) - 명령어의 직합

### 1-1. 프로세스 메모리 구조

![process1](https://raw.githubusercontent.com/CSFarming/CSFarming-Archive/master/OperatingSystem/Asset/process1.png)

|주제|내용|
|---|---|
|Stack|지역 변수, 매개 변수 등이 저장되는 영역. 컴파일 때 크기 결정|
|Heap|사용자가 동적으로 할당하는 영역. 런타임 때 크기 결정|
|Data|전역 변수, 정적 변수가 저장되는 영역. 프로그램이 시작되고 끝날 때 까지 메모리에 존재|
|Code|컴파일된 코드가 저장. 즉 CPU가 실행할 명령어가 저장되어 있음|

- 메모리 영역은 한정적이기 때문에 이에 따른 문제가 있을 수 있음
- 스택 영역을 초과하면 스택 오버플로우(Stack Overflow)라고 함
- 힙 영역을 초과하면 힙 오버플로우(Heap Overflow)라고 함

### 1-2. 프로세스 제어 블록
- OS에서 프로세스를 관리하기 위해서는 프로세스 정보가 필요함
- 프로세스 제어 블록(Process Control Block, PCB)는 프로세스에 대한 중요한 정보를 저장하는 자료 구조

![process2](https://raw.githubusercontent.com/CSFarming/CSFarming-Archive/master/OperatingSystem/Asset/process2.png)

#### PCB가 존재하는 이유
- 모든 프로세스가 CPU를 동시에 사용할 수 없음
- 즉 프로세스는 **CPU의 스케줄링을 통해 프로세스들에게 적절하게 CPU를 점유할 수 있도록 함**
- 진행 중인 프로세스가 멈췄다가 **다시 실행하기 위한 정보**가 필요한데 이 정보가 PCB

### 1-3. Context Switching
- 프로세스는 CPU 스케줄링을 통해 CPU를 점유함

![process3](https://raw.githubusercontent.com/CSFarming/CSFarming-Archive/master/OperatingSystem/Asset/process3.png)

![process4](https://raw.githubusercontent.com/CSFarming/CSFarming-Archive/master/OperatingSystem/Asset/process4.png)


#### Process 1에서 Process 2로 Context Switching
1. Process 1이 먼저 메모리에 Process 1의 PCB를 저장함
2. Process 2의 PCB를 가져옴
3. Process 2를 실행

- 이처럼 **PCB를 저장 및 복구**를 하고 **새로운 프로세스를 실행**하는 것을 **Context Switching** 이라고 함

### 1-4. 프로세스 상태
- PCB 내부에는 프로세스 상태(Process State)도 저장

![process5](https://raw.githubusercontent.com/CSFarming/CSFarming-Archive/master/OperatingSystem/Asset/process5.png)

|상태|내용|
|--|--|
|생성(new)|메모리에 적재되어 PCB 할당을 받은 상태|
|준비(ready)|CPU 할당을 받아 실행할 수 있는 상태|
|실행(running)|CPU를 할당 받아 실행 중인 상태|
|대기(waiting)|입출력 신호 또는 이벤트가 발생하여 프로세스가 대기 중인 상태. 입출력 완료, 시그널 수신 등 이벤트를 기다림|
|종료(terminated)|프로세스가 종료된 상태|

- 디스패치(dispatch): ready 상태에서 running 상태로 바뀌는 것
