
```java
class Solution {
    public String solution(String s) {
        String answer = "";

        String[] sp = s.split(" ");

        for (String spu : sp) answer += run(spu);

        return (s.charAt(s.length() - 1) == ' ')
            ? answer
            : answer.substring(0, answer.length() - 1);
    }

    private String run(String target) {
        if(target.length() == 0) return " ";

        StringBuilder sb = new StringBuilder();

        sb.append(target.substring(0, 1).toUpperCase());
        sb.append(target.substring(1, target.length()).toLowerCase());
        sb.append(" ");

        return sb.toString();
    }
}
```

### 플랫폼
- 프로그래머스

### 난이도
- 2레벨

### 문제
```
JadenCase란 모든 단어의 첫 문자가 대문자이고, 그 외의 알파벳은 소문자인 문자열입니다. 단, 첫 문자가 알파벳이 아닐 때에는 이어지는 알파벳은 소문자로 쓰면 됩니다. (첫 번째 입출력 예 참고)  
문자열 s가 주어졌을 때, s를 JadenCase로 바꾼 문자열을 리턴하는 함수, solution을 완성해주세요.
```

### 아이디어
1. 입력값 크기가 크지 않다.
2. *공백이 연속해서 나올 수 있고, 마지막이 공백으로 끝나는 경우에 대해 처리해주면 된다.*