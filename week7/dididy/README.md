# 7주차 문제

## 가장 큰 수 - Lv2
처음에는 순열을 이용해 구하면 되겠지 싶었는데 수가 너무 커지기 때문에 이렇게 접근하면 안된다.

자바스크립트의 sort는 문자열을 기준으로 한다. 처음에는 sort와 reverse 메서드를 같이 쓰면 풀리겠다고 생각했는데 아니었다.

[3, 30, 34, 5, 9] 일 경우에 sort와 reverse를 사용해 구하면 9534303로 기대값 9534330보다 작은 수를 구하게 된다.

따라서 이부분에 대해서는 따로 처리해주어야 한다. 문자열 순서를 바꿔서 더한 값을 각각 비교해서 큰 값을 기준으로 정렬하도록 처리했더니 최대값을 구할 수 있었다.

## 멀쩡한 사각형 - Lv2
문제의 조건인 가로가 8, 세로가 12인 직사각형을 생각해 봤을 때 직선과 겹치는 구간을 사각형 범위로 확장해보면 해당 사각형의 가로 세로 길이는 원래 길이에 최대공약수를 나눈 값이라는 것을 알 수 있다. 그리고 해당 사각형은 최대공약수만큼 반복한다.

일반화 시켜 보면 위에서 정의한 사각형에서 실제로 선과 겹치는 부분은 세로 - 1을 한 것과 같다.

1. 최대공약수를 나눈 각각의 가로, 세로 길이를 구한다.
2. 가로 와 세로 - 1을 한 값을 곱한다.
3. 최대공약수만큼 반복한다.

이렇게 식을 도출하여 적용하면 문제를 해결할 수 있다.

## 광고 삽입 - Lv3
함수를 만들어 시간 문자열을 초단위로, 초단위를 시간 문자열로 바꿀 수 있도록 한다.

playTime과 advTime을 함수를 통해 초단위로 바꾸고 viewer 배열을 만들어서 시청자 및 누적 시청자를 구할 수 있도록 구현했다.

누적 시청자에서 가장 시청자가 많은 부분을 찾도록 하면 된다.


