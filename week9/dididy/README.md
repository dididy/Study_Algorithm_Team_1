# 9주차 문제

## 땅따먹기 - Lv2
N행의 땅을 하나씩 내려올 때 같은 열을 밟으면 안되는 규칙으로 가장 큰 값을 구하는 문제이다.

간단하게 구할 수 있는데 두번째 행 부터 각각의 열마다 같은 열이 아닌 이전 행의 값 중 가장 큰 값을 더하고 이것을 반복하면 된다.

이렇게 구하게 되면 각각의 행의 열마다 가장 큰 값을 더해나간 꼴이 되므로 마지막 행의 값 중 가장 큰 값이 최고점이 된다.

## 쿼드압축 후 개수 세기 - Lv2
정사각형은 4등분으로 쪼개가면서 압축할 수 있는 부분은 압축하고 최종적으로 압축을 완료했을 경우 0, 1이 각각 몇개인지를 구하는 문제이다.

재귀를 사용하여 풀면 된다.

재귀 함수를 만들어 전체가 1 혹은 0이 될 때를 탈출조건으로 걸고 각각 [0, 1], [1, 0]을 return 하도록 한다.

함수 내부적으로는 4등분한 각각을 재귀적으로 호출하도록 하고 위의 규칙대로 return된 값을 기반으로 0의 갯수 및 1의 갯수를 더하여 최종적으로 반환하도록 한다.

## 여행 경로 - Lv3