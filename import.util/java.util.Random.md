### 범위 지정하여 랜덤한 수를 생성하는 방법

#### 우선 wRandom object를 선언 후, 생성해야 함.
* ex. Random random = new Random();

* ex. int randomInt = random.nextInt(10)+1; //1에서 10 사이의 정수
- 만약 +1을 하지 않는다면, 0에서 9까지의 범위로 생성됨.

* 범위를 정할 때, 최솟값이 0이 아니라면, 최솟값만큼 더해주면 된다.
- int randomInt = random.nextInt(max - min + 1) + min;

* 출처 및 참조 : https://priming.tistory.com/99