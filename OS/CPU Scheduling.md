# 스케줄링
    CPU를 잘 사용하기 위해 프로세스를 배정하는 법
    
    1. Batch System: 가능하면 많은 일을 수행, 시간보다 처리량이 중요
    2. Interactive System: 빠른 응답기간, 적은 대기시간
    3. Real-time System: 기한 맞추기

# 선점 / 비선점 스케줄링

    선점(preemptive): OS가 CPU의 사용권을 선점, 강제회수하는 경우(처리시간의 예측이 어려움)
    
    비선점(nonpreemptive): 프로세스 종료 or I/O 등의 이벤트가 있을 때 까지 실행시간을 보장(처리시간 예측 용이)

# 프로세스의 상태 전이 
    승인(Admitted): 프로세스 생성이 가능하여 승인됨

    스케줄러 디스패치 (Scheduler Dispatch) : 준비상태에 있는 프로세스 중 하나를 선택하여 실행시키는 것

    인터럽트 (Interrupt) : 예외, 입출력, 이벤트 등이 발생하여 현재 실행 중인 프로세스를 준비 상태로 바꾸고 해당 작업을 먼저 처리하는 것 

    입출력 또는 이벤트 대기 (I/O or Event wait): 실행 중인 프로세스가 입출력이나 이벤트를 처리해야 하는 경우 끝날 때까지 대기상대로 만드는 것

    입출력 또는 이벤트 완료 (I/O or Event Completion) : 입출력/이벤트가 끝나 프로세스를 준비상태로 전환하여 스케줄러에 의해 선택 될 수 있도록 만드는 것

# CPU 스케줄링의 종류

    ○ 비선점 스케줄링
        - FCFS(First Come First Served
            큐에 도착한 순서대로 CPU 할당
            실행 시간이 짧은 것이 뒤에 할당 되면 대기시간이 길어짐

        - SJF(Shortest Job First)
            수행시간이 가장 짧은 작업을 먼저 수행
            FCFS 보다 평균 대기시간이 감소, 짧은 작업에 유리

        - HRN (Hightest Response-ratio Next)
            우선순위를 계산하여 점유 불평등을 보완한 방법
            우선순위 = (대기시간 + 실행시간) / 실행시간

    ○ 선점 스케줄링
        - Priority Scheduling
            정적/동적으로 우선순위를 부여하여 우선순위가 높은 순서로 처리
            우선 순위가 낮은 프로세느가 무한정 기다리는 Starvation 발생 가능
            Aging 방법으로 Starvation 문제 해결

        - Round Robin
            FCFS에 의해 프로세스들이 보내지면 각 프로세스는 동일한 시간의 Time Quantum 만큼 CPU를 할당 받음
            할당시간이 크게 되면 FCFS와 같게 되며 작게되면 Context Switching이 증가하여 오버 헤드가 증가

        - Multilevel-Queue
            작업들을 여러 종류의 그룹으로 나누어 여러 큐를 이용하는 기법
            우선순위가 낮은 큐들이 실행하지 못하는 것을 방지하고자 Time Quantum을 설정

# CPU 스케줄링 척도
    1. Response Time : 작업이 처음 실행 되기까지 걸린 시간

    2. Turnaround Time : 실행 시간과 대기 시간을 모두 합한 시간으로 작업이 완료될 때 까지 걸린 시간