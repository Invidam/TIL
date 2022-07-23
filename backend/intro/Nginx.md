# NginX

## Nginx란?

(공식 사이트 소개글 중)

Nginx는 무료, 오픈소스, 고성능 **HTTP 서버**이고 **리버스 프록시**입니다. 

**C10K 문제** 해결을 위해 **등장**하였고, **이벤트 기반 (비동기) 아키텍처**를 사용합니다.

## 등장 배경

- C10K 문제의 해결을 위해 등장하게 됨.

### C10K

- 뜻: 1만 개의 클라이언트 문제
- 내용: 많은 클라이언트를 동시에 처리하도록 네트워크 소켓을 최적화하는 문제이다.

### 기존 웹 서버로 많이 사용했던 Apache의 문제점

- 클라이언트의 접속마다 프로세스를 생성한다.
    - 많은 사용자가 있으면, 과부하가 생긴다.

### Nginx의 해결 방안

- 이벤트 기반 아키텍처를 사용하여 해결

## 이벤트 기반 아키텍쳐

### Nginx의 이벤트 처리과정 (Event-Driven)

1. Nginx는 많은 이벤트들을 수신한다.
2. 수신한 이벤트들은 큐에 저장된다.
3. 대기하고 있던 Worker Process가 이를 처리한다.

### 프로세스 특징

- 한 개의 Master Process가 여러 개의 Worker Process(일반적으로, CPU 코어의 수 만큼)를 생성함.
- Worker Process가 요청을 처리함.
    - Worker Process는 하나의 요청만을 처리하지 않고 여러 연결 및 요청을 처리할 수 있음.
        
        → 프로세스 수 ↓ → 효율적 처리
        
        1. Context Switching ↓
            - Context Switching: CPU위에 실행 중이던 프로세스를 다음 프로세스로 교체하는 작업 (많이 일어날 경우 성능이 하락함.)
        2. 프로세스 생성, 제거 비용 ↓
- 시간이 오래 걸리는 작업은 Worker Process가 처리하지 않고, 쓰레드 풀에 맡긴 뒤, 다른 작업을 처리한다.
    - Non-Blocking
    - Async
    

## HTTP Server

(= Web Server)

- 클라이언트의 HTTP Request에 대해 정적인 파일(html 문서, 이미지, 등)을 반환해주는 서비스

## 리버스 프록시

### 프록시 서버

- 일반적으로, Forward Froxy를 의미함.
- 클라이언트와 시스템서버 사이에 위치함.
- 보안, 캐싱, 트래픽 차단 등의 기능을 수행함.

### 리버스 프록시

- Forward Froxy와는 다르게, 인터넷 뒤에 위치하여 있음.
    - Client ↔ Internet ↔ Reverse Proxy ↔ Server 의 구성
- 특징
    - Forward Froxy가 클라이언트를 보호하는 것과 반대로, 서버를 보호하는데 사용함.
        - 클라이언트는 프록시 서버와 통신하고, 실제 서버와는 통신하지 못해 서버가 어떤 처리를 하였는지 알지 못함.

- 참고
    - [https://www.nginx.com/resources/wiki/](https://www.nginx.com/resources/wiki/)
    - [https://www.nginx.com/blog/thread-pools-boost-performance-9x/](https://www.nginx.com/blog/thread-pools-boost-performance-9x/)
    - [https://www.strongdm.com/blog/difference-between-proxy-and-reverse-proxy](https://www.strongdm.com/blog/difference-between-proxy-and-reverse-proxy)