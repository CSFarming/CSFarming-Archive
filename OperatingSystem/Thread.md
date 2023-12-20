## 1. 스레드
- 스레드(Thread)는 프로세스 내에서 실행되는 흐름의 단위
- 스레드는 Stack 영역에 존재함
- 프로세스는 1개 이상의 스레드를 가짐

![thread1](https://raw.githubusercontent.com/CSFarming/CSFarming-Archive/master/OperatingSystem/Asset/thread1.png)


### 1-1. 멀티 스레드
![thread2](https://raw.githubusercontent.com/CSFarming/CSFarming-Archive/master/OperatingSystem/Asset/thread2.png)

- 하나의 프로세스는 한 번에 여러 일을 동시에 처리할 수 있음 (동시성)
- 동시성(Concurrency): 하나가 여러 작업을 번걸아 가면서 처리하여 마치 동시에 작업을 진행하는 것처럼 보임
- 병렬성(Parallelism): 여러 개가 여러 개의 작업을 처리(실제로 동시에 처리)

![thread3](https://raw.githubusercontent.com/CSFarming/CSFarming-Archive/master/OperatingSystem/Asset/thread3.png)

- 멀티 스레드는 같은 프로세스의 자원을 공유
- 스레드 간의 전환 속도가 프로세스 간 전환 속도보다 빠름
- 멀티 스레드에서는 **하나의 스레드가 문제가 생기면 모든 스레드에 영향을 줌**


### 1-2. 멀티 스레드 & 멀티 프로세스
![thread4](https://raw.githubusercontent.com/CSFarming/CSFarming-Archive/master/OperatingSystem/Asset/thread4.png)

|멀티 스레드|멀티 프로세스|
|--|--|
|빠른 Context Switching|느린 Context Switching|
|적은 리소스 사용(시간, 메모리)|많은 리소스 사용(시간, 메모리)|
|하나의 스레드가 모든 스레드에 영향|다른 프로세스에 영향을 주지 않음|
