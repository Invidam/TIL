# Redis

## Redis란?

Redis는 **key-value** 형식의 **In-memory** DB이다.

- 주로 캐싱 용도로 사용한다.
    - e.g.  좋아요 기능, 유저 수 확인 등

## 특징

### 다양한 컬렉션 타입을 지원한다.

- `Strings` : 문자열
- `Lists` : 링크드 리스트
- `Sets` : 정렬되지 않는 집합
- `Sorted sets` : score을 입력해 정렬한 집합
- `Hashes` : key-value 의 자료구조
- `Bitmaps` : 비트들의 Map
- `HyperLogLogs` : 알고리즘을 통해, 집합의 원소 개수를 효율적으로 추정
    - 참조: [https://d2.naver.com/helloworld/711301](https://d2.naver.com/helloworld/711301)
- `Streams` : 주로 로그 데이터에 사용하는 자료구조

### In-memory

- 메모리에 데이터를 저장 → 처리 속도 ↑
- 저장 공간 한정

### Expire

- 인 메모리의 적은 저장 공간을 보완하기 위한 권장되는 기능.
- 데이터의 사용 기한을 지정하여 삭제를 Redis에게 맡김.

### Persistency

- 인 메모리의 특징인 휘발성을 해소하기 위해 SSD와 같은 저장소에 저장하는 것
    - RDB
        - 특정 간격으로 저장함.
    - AOF
        - 모든 작업을 기록함.

### Single Thread

- Context Switcing 발생 X
- 원자성 (Atomic) 보장
    - Race Condition X
        - Race Condition: 여러 입력이 같이 일어나, 원치 않는 결과가 나타나는 것
- 시간 복잡도가 큰 (`O(N)` ) 명령을 주의

### Cluster

- Scale out을 통해 데이터 분산
- 장애 대처 용이 (다른 노드가 있으므로)

### Replication, Cluster, Failover

- 참고
    - [https://redis.io/docs/about/](https://redis.io/docs/about/)
    - [https://sjh836.tistory.com/178](https://sjh836.tistory.com/178)
    - [https://medium.com/garimoo/개발자를-위한-레디스-튜토리얼-01-92aaa24ca8cc](https://medium.com/garimoo/%EA%B0%9C%EB%B0%9C%EC%9E%90%EB%A5%BC-%EC%9C%84%ED%95%9C-%EB%A0%88%EB%94%94%EC%8A%A4-%ED%8A%9C%ED%86%A0%EB%A6%AC%EC%96%BC-01-92aaa24ca8cc)
    
- 참고 예정
    - [https://taes-k.github.io/2020/07/23/redis-essential/](https://taes-k.github.io/2020/07/23/redis-essential/)
    - [https://velog.io/@hyeondev/Redis-란-무엇일까#redis-replication](https://velog.io/@hyeondev/Redis-%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%BC%EA%B9%8C#redis-replication)
    - [https://ict-nroo.tistory.com/133](https://ict-nroo.tistory.com/133)
    - [https://akasai.tistory.com/23](https://akasai.tistory.com/23)
    