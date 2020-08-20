# Ch4. Threads
## 1. Processes and Threads
- Resource Ownership
  > 프로세스는 프로세스 이미지와 다른 자원을 가지기 위해 가상 주소 공간을 포함한다.

- Scheduling / Execution
  > 프로세스의 실행은 다른 프로세스들과 상호작용한다. 어떻게 상호작용할지에 대한 방식은 스케줄링 기법에 따라!

- dispatching의 단위는 thread 혹은 lightweight process라 불린다.
- resource ownership의 단위는 process 혹은 task로 불린다.
- Multithreading
  > 단일 프로세스 내에서 다중, 동시적 경로로 실행할 수 있게 OS가 지원해주는 기능
<br/>

## 2. Threads
- 각 쓰레드는 실행 상태를 지닌다.(ex. Running, Ready, etc)
- 실행중이 아니라면 thread context를 저장한다.
- 실행 스택을 가진다.
- 프로세스내 메모리, 자원에 접근가능하며 같은 프로세스내 존재하는 다른 쓰레드들과 공유한다.
- Multithread process model에서는 single thread process model과 달리 pcb만 존재하는게 아니라 더 작은 크기의 tcb(thread control block)의 정보만 바꿔서 스케줄링한다.

- 프로세스에 존재하는 모든 쓰레드에 영향을 주는 행위
* Suspending : 프로세스가 suspend되면 모든 쓰레드 또한 suspend 된다. 왜냐하면 프로세스내 쓰레드들은 모두 같은 공간 주소를 공유하고 있기 때문이다.
* Termination : 프로세스가 메인 메모리에서 삭제되면 프로세스내 모든 쓰레드 또한 삭제된다.

<br/>
## 3. Key benefits of Threads
쓰레드의 장점 4가지를 살펴보자.
- 프로세스를 새로 생성하는것 보다 쓰레드를 만드는데 걸리는 시간이 더 적다.
- 프로세스를 종료하는데 걸리는 시간보다 쓰레드를 종료하는데 걸리는 시간이 더 짧다.
- 프로세스간의 교환보다 쓰레드간의 교환이 시간적으로도 적고 오버헤드도 적다.
- 쓰레드는 실행중인 다른 프로그램간의 효율적인 소통을 강화시켜준다.
