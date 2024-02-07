---
title: "dashboard configuration"
date: 2024-02-07 +0900
categories: [Webmethods Administrator, 대시보드 사용]
tags: [EAI, webmethods, Administrator]
---

대시보드에 표시되는 통계를 수집하고 저장하는 데에는 메모리, JDBC 풀 연결, 스레드, 디스크 공간 등 IS 서버 리소스가 사용됩니다. IS 관리자 페이지에서는 대시보드에 사용되는 리소스를 제한하는 옵션을 사용 할 수 있습니다

> 참고: dashboard configuration에 대한 모든 옵션은 Integration_Server_directory/instances/instanceName/config/monitor/monitor.cnf로 사용 가능한 구성 매개변수를 통해 설정할 수 있습니다
> 

![Untitled](/assets/img/2024-02-07-대시보드_configuration/Untitled.png)

**Statistics data collection**

- 통계 데이터 수집기의 활성의 활성화 여부입니다.
- 비활성화 되면 통계 데이터 수집기는 리소스를 소비하지 않으며 통합 서버에 오버헤드를 추가하지 않습니다. 통합 서버가 엔터프라이즈 게이트웨이 서버 역할을 하는 경우와 같은 일부 환경에서는 통계 데이터 수집기를 비활성화 할 수 있습니다.

**Maximum number of results**

- 통계 데이터 수집기에서 허용되는 최대 결과 수 입니다. 최소값은 1입니다
- 기본값 : 1500000
- 이 옵션은  monitor.cnf의 maxResults 매개변수에 해당합니다.

**Memomry size (MB)**

- 통계 데이터 수집기에 전용으로 사용할 JVM 메모리 베가바이트 수입니다. 최소값은 256입니다.
- 기본값: 256
- 이 옵션은 monitor.cnf의 luceneMemorySize 매개변수에 해당합니다.

**Indexer thread count**

- 동시에 인덱싱 할 수 있는 리소스 수 입니다. 사용 가능한 스레드보다 인덱스 작업이 더 많은 경우 해당 작업은 스레드를 사용할 수 있을 때 까지 기다립니다. 인덱서 스레드는 별도의 스레드 풀에서 나옵니다. 즉 , 인덱서 스레드는 서버 스레드 풀에서 가져온 것이 아닙니다. 최소값은 2입니다.
- 기본값: 8
- 이 옵션은 monitor.cnf indexerThreadCount 매개변수에 해당합니다.

**Searcher thread count**

- 동시에 실행할 수 있는 검색 요청 수입니다. 검색 요청수가 이 값을 초과하면 보류중인 검색 요청은 현재 실행중인 검색 요청이 완료될 때까지 차단 됩니다. 최소값은 2입니다.
- 기본값: 8
- 이 옵션은 monitor.cnf의 searcherThreadCount 매개변수에 해당합니다.

**Retention days**

- 통계 데이터 수집기에서 사용하는 데이터베이스에 데이터를 보관하는 최대 일수입니다. 최소값은 1입니다.
- 기본값: 30
- 이 옵션은 monitor.cnf의 retentionDays매개변수에 해당합니다.

> 참고: 대시보드 구성을 변경해도 통계 데이터 수집기가 다시 시작되지는 않습니다. 그러나 통계 데이터 수집기를 비활성화하면 종료도고
>