# RabbitMQ 테스트
> tacomo 에 사용할 rabbitMQ 테스트 
```
rabbitMQ는 우편함이자 우편국, 우편집배원이다 - rabbitMQ introduction...
5672 amqp port
15672 웹 관리 콘솔
guest/guest

rabbitMQ connection은 소켓커넥션을 추상화, 프로토콜 버전 협상 및 인증 등을 대신 해줌,
Connection과 Channel은 java.io.Closeable을 구현하기 때문에 try-with-resources 선언을 할 수 있따. 따라서 코드 뒷부분에 따로 close 안해줘도 된다

example 01 ~ 02 구조
producer -> queue -> consumer...

example 03~... 구조
producer -> exchange -> queue .....

exchangeType
    fanout : 전체 뿌리기
    direct : 특정 routing key에만 모든 큐가 같은 routing key 가지고있으면 fanout마냥 동작
    topic : .으로 구분되는 word의 집합 라우팅키를 이용 * # 이용 *반드시하나의 단어 #없거나 더 많은 word
```
* gradle
    - install https://docs.gradle.org/current/userguide/installation.html
    - init https://docs.gradle.org/current/samples/sample_building_java_applications.html


* rabbitmq
    - to start : docker run -d --rm --name rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq:3-management