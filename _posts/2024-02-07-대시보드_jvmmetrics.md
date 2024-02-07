---
title: "JVM metrics tab"
date: 2024-02-07 +0900
categories: [Webmethods Administrator, 대시보드 사용]
tags: [EAI, webmethods, Administrator]
---

JVM(Java Virtual Machine) Metric 탭을 사용하면 IS 서버가 실행되는 JVM의 힙 메모리, 스레드 요약 및 가비지 수집 세부 정보를 볼 수 있습니다. 또한 CPU 및 메모리 사용량과 같은 운영 체제 리소스 정보를 시간에 따라 볼 수도 있습니다.

> 참고:
JVM 메트릭 탭에는 현재 통합 서버 인스턴스의 데이터만 표시됩니다. 이 데이터는
java.lang.management.MemoryPoolMXBean 클래스 에서 보고하는 데이터입니다 .
> 

![Untitled](/assets/img/2024-02-07-admin-dashboard-jvmmetrics/Untitled.png)

그래프의 항목들은 다음과 같습니다.

### **Memory Usage (MB)**

---

![Untitled](/assets/img/2024-02-07-admin-dashboard-jvmmetrics/Untitled%201.png)

- **Heap used**
    - 힙에 사용된 메모리 양(MB)을 표시합니다.
- **Non heap used**
    - JVM이 클래스의 필드 및 메소드, 메소드 코드, 런타임 상수 풀 및 내부화된 문자열과 같은 클래스 수준 정보를 저장하는 곳입니다. JVM에서 사용하는 힙이 아닌 메모리의 양(MB)을 표시합니다.

### CPU Usage (%)

---

![Untitled](/assets/img/2024-02-07-admin-dashboard-jvmmetrics/Untitled%202.png)

- **System CPU**
    - 전체 시스템의 CPU 사용량입니다. 0% 값은 모든 CPU가 유휴 상태임을 의미하고, 100% 값은 관찰 간격 동안 모든 CPU가 실행 중임을 의미합니다.
- **Process CPU**
    - JVM 프로세스의 CPU 사용량입니다
    

### **Thread summary**

---

![Untitled](/assets/img/2024-02-07-admin-dashboard-jvmmetrics/Untitled%203.png)

- Wating
    - 다른 스레드가 특정 작업을 수행하기를 무기한 기다리는 스레드 수입니다.
- Timed wating
    - 지정된 대기 기간 동안 다른 스레드가 작업을 수행하기를 기다리는 스레드 수 입니다.
- Runnable
    - JVM에서 실행 중인 스레드 수입니다.

 

### CPU vs running threads

---

![Untitled](/assets/img/2024-02-07-admin-dashboard-jvmmetrics/Untitled%204.png)

- **Running thread count**
    - JVM에서 실행 중인(실행 가능 상태에서) 총 스레드 수 입니다.
- **JVM CPU(%)**
    - JVM 프로세스의 CPU 사용량 입니다.

### **Garbage collector summary**

---

![Untitled](/assets/img/2024-02-07-admin-dashboard-jvmmetrics/Untitled%205.png)

> 참고:
GC(가비지컬렉션)는 JVM에 특정하며 아래 설명된 것과 다를 수 있습니다.
> 

**JVM의 가비지 컬렉션에는 크게 두 영역이 존재합니다**

- Young Generation ( 새로 생성된 객체가 위치하는 곳)
- Old Generation ( Young Generation에서 여러 차례의 가비지 컬렉션을 거치고도 살아남은 객체들이 위치하는 곳)

- **G1 Young Generation**
    - Young Generation의 Eden 및 Survivor영역에서 수집한 Garbage 수 입니다
- **G1 Old Generation**
    - Old Generation 영역에서 확보한 Garbage 수 입니다.
- **G1 Young Generation(ms)**
    - Young Generation의 Eden 및 Survivor영역에서 메모리를 확보하는데 걸린 시간입니다.
- **G1 Old Generation(ms)**
    - Old Generation ****영역에서 메모리를 확보하는데 걸린 시간 입니다.

### **Heap memory usage** (MB)

---

![Untitled](/assets/img/2024-02-07-admin-dashboard-jvmmetrics/Untitled%206.png)

- **Old Gen**
    - Old Generation 메모리에 사용된 메모리 양(MB)입니다.
- **Survivor Space**
    - Young Generation 메모리의 Survivor 영역에 사용되는 메모리 양(MB)입니다.
- **Eden Space**
    - Young Generation 메모리의 Eden 영역에 사용된느 메모리 양(MB)입니다.