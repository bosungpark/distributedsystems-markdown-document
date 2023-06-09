분산 시스템이란?
=

- 빛의 속도로 이동하는 정보를 다루는 것 -> 거리
- 독립적으로 실패하는 문제를 다루는 것 -> 여러 데이터

컴퓨터의 주요한 업무는 1. 데이터 저장, 2. 연산이다.
분산 시스템은 하나의 컴퓨터로 해결하던 문제를 여러 대의 컴퓨터로 해결하는 것이다.

수량이 많아지면 다루기가 어려워진다.
=
Scalability: ...

  - size scalability: node의 수를 늘리는 것.
  - geographic scalability: 데이터 센터간의 지연관리.
  - administrative scalability: node의 수를 늘리는 것이 운영을 방해해서는 안된다.


Performance(and latency)

  - 응답시간, 지연, 처리량, 자원의 이용량 등을 통해 측정할 수 있다.
  - 응답에 대한 지연을 줄여 즉각적인 반응을 이끌어내는 것은 돈을 들이더라도 해결하기 여려운 문제이다.
  - 지연: 무언가 사건이 이미 발생했지만, 발견되지 않고 감취진 동안의 시간.
  - 지연이 있다는 것은 데이터의 변경이 있었다는 것. 분산시스템에서는 최소한 빛의 속도만큼의 지연이 있다.

Availability(and fault tolerance)

  - 사용자가 서비스를 이용할 수 있는 지, Availability = uptime / (uptime + downtime)
  - 단일 시스템은 전부 성공 혹은 전부 실패, 하지만 분산 시스템은 신뢰성 없는 컴포넌트를 이용해 신뢰할 수 있는 시스템을 만들어야 한다는 도전과제가 있다.
  - redundancy가 없는 시스템은 컴포넌트만큼만 가용하지만, redundancy가 있는 시스템은 부분 실패 등에 있어서 더 가용한 특징을 가진다.
  -  기술적 관점에서 Availability는 대부분 내결함성(fault tolerance)과 관련이 있다. 컴포넌트가 늘어날 수록, 부분 실패의 가능성 역시 커지기 때문이다.

분산 시스템을 어렵게 하는 것
=
1. 노드의 수
2. 노드의 거리

추상화
=
- 시스템 모델(동기/비동기)
- 실패 모델(crash-fail/partition/Byzantine)
- 일관성 모델(strong, eventual)

분산 시스템을 하나의 시스템처럼 보이게 만드는 비용은 크다. 만약 gurantee를 조금 약하게 가져간다면 더 많은 자유를 확보할 수 있다.

patition, replicate
=
분산 시스템의 문제를 푸는 가장 중요한 두 테크닉.

patition: 데이터를 작은 집합으로 쪼게는 것. 파티셔닝 전략은 어플리케이션 특이적인 면이 있다.

replicate: 데이터를 다양한 머신에 복제하는 것. 더 많은 서버에서 연산을 할 수 있는 여지를 준다. 또 내결함성을 향상 시켜준다. (Scalability, Performance, Availability) 하지만 동시에 데이터 싱크와 같은 다양한 문제를 가져오기도 한다.
