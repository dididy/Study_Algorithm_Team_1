# 2주차 문제 풀이

## 문제 링크

- [순위 검색](https://programmers.co.kr/learn/courses/30/lessons/72412?language=javascript) - 레벨 2
- [JadenCase 문자열 만들기](https://programmers.co.kr/learn/courses/30/lessons/12951) - 레벨 2
- [가장 긴 팰린드롬](https://programmers.co.kr/learn/courses/30/lessons/12904) - 레벨 3

## 문제 풀이

### 순위 검색
순위 검색은 풀다가 실패하여 다른 분의 풀이를 참고했습니다. 
- https://bit.ly/3t7E4F6

소스에는 `순위검색_fail.test.js` 파일도 존재하는데, 제가 처음 시도한 풀이 방법이 담겨있는 소스파일입니다.

이 소스의 풀이는 하나의 `info` 원소에 대해서 javascript 객체로 트리 구조를 만들었습니다. *key-value 쌍인 객체로 원소를 순회하면 빠르게 찾아낼 수 있지 않을까?* 하는 생각에 시도한 방법인데, 아무리 객체여도 너무 많은 key값을 탐색하기에는 효율성에서 시간 초과가 발생하더군요.

일단 git에 올린 이유는 객체의 key-value로 추가하는 함수가 추후에 쓸 일이 있지 않을까 해서 올렸습니다. 소스의 `makeTree` 에 대한 함수와 테스트 케이스를 참고해 주시기 바랍니다.

---

### JadenCase
풀이는 아래와 같습니다.

1. split 메서드를 사용해서 입력으로 들어온 문자열을 공백 기준으로 나누어 배열을 만듭니다.
2. 배열의 원소 하나에 대해서 change 메서드를 호출합니다.
3. 인자로 들어온 단어의 첫 글자가 영문자인지 정규식을 이용해 판단합니다.
    1. true 라면 change메서드는 toLowerCase와 toUpperCase 메서드로 대->소, 소->대 문자를 만듭니다.
    2. false 라면 입력된 그대로 반환합니다.

`charAt` 메서드는 인자의 숫자에 해당하는 index 위치에 있는 문자를 반환합니다.

---

### 가장 긴 펠린드롬

가장 단순한 풀이방법은 현재 위치를 기점으로 왼쪽과 오른쪽 순회를 해 보는 것입니다.

`pailndrome` 메서드는 인자로 문자열과 왼쪽, 오른쪽의 index를 받습니다.

문자열의 범위를 넘어서지 않고, 순회 하면서 두 index 위치의 문자가 서로 같다면 계속해서 순회를 진행합니다.

서로 달라지는 순간에 두 index의 차이값을 반환하여 펠린드롬의 길이를 반환하게 됩니다.

`-1`이 들어가는 이유는 다음과 같습니다.
```
입력: 'abcdcba
호출: pailndrome('abcdcba', 3, 3)

첫 시작부터 s[l] === s[r] 이므로 l: 2, r: 4
계속 진행되면
l: 1, r: 5
l: 0, r: 6
while문 탈출 시
l: -1, r: 7

return r - l - 1 => 7 - (-1) - 1 = 7
```

문자열의 길이가 홀수일 경우는 `l: x, r: x` 로 동일하고, 짝수일 경우는 `l: x, r: x + 1` 로 하여 펠린드롬을 호출합니다.

`Math.max()` 를 이용해 최대값을 찾아 반환합니다.

---