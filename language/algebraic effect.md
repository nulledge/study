# 대수적 효과

대수적 효과(Algebraic effect)를 한 문장으로 요약하면 '**무엇을 어떻게 할지 정의한 코드**'를 '**무엇을 할지 정의한 코드**'와 '**어떻게 할지를 정의한 코드**'로 분리하는 방법이다.

## 용어 뜻풀이

대수(Algebra, 代數)는 복잡한 수(數)를 간단한 문자로 대체해서(代) 식을 작성하는 방법을 의미한다.
효과(effect)는 정보과학 관점에서 연산 과정의 결과로 상태를 변경시키는 작용을 의미한다.
따라서 대수적 효과의 의미를 풀어서 이해하면 **연산 과정에서 상태를 변경시키는 부분을 간단한 문자로 대체하는 방법**을 의미한다.

## 대수적 효과 수행

`try/catch`는 많은 프로그래밍 언어에서 작업 도중 발생한 오류를 해결할 때 사용하는 문법이다.
이때 중요한 점은 `try`에 *무엇*을 할지 정의하지만, *어떻게* 오류를 해결할지는 정의하지 않고 신경쓰지도 않는다.
*어떻게* 오류를 해결할지는 `catch`에 정의한다.

비슷하게 대수적 효과 수행(algebraic effect handler) 문법으로 `try/handle`을 고려할 수 있다.
`try`에는 *무엇*을 할지 정의한다. 그리고 `catch`에는 이를 *어떻게* 수행할지 정의한다.

### 예시

```javascript
function getName(user) {
  let name = user.name;
  if (name === null) {
    name = perform 'ask_name';
  }
  return name;
}

function makeFriends(user1, user2) {
  user1.friendNames.add(getName(user2));
  user2.friendNames.add(getName(user1));
}

const arya = { name: null };
const gendry = { name: 'Gendry' };
try {
  makeFriends(arya, gendry);
} handle (effect) {
  if (effect === 'ask_name') {
    resume with 'Arya Stark';
  }
}
```

`try`에는 `ask_name`이라고 *무엇*을 수행할지 정의한다. 여기서는 이름이 비어있을 때 채우는 작업을 의미한다.
`handle`에는 `ask_name`이라고 수행할 작업이 주어졌을 때 *어떻게* 수행할지 정의한다. 여기서는 Arya Stark라는 이름을 사용하기로 정했다.

코드를 수정해 키보드로 이름을 입력받거나, 음성인식으로 이름을 받아적는 경우를 생각하면 대수적 효과의 장점을 이해할 수 있다.
키보드를 사용하거나, 음성인식을 사용하거나. 모두 *어떻게* 이름을 채우는지 방법에 해당한다.
*무엇*을 할지, 그러니까 이름이 비어있을 때 이름을 채워야 한다는 작업은 변하지 않는다.
즉, `try`의 코드는 그대로 두고 `handle`의 코드만 수정하면 된다.

# 참고
- [모두를 위한 대수적 효과](https://overreacted.io/ko/algebraic-effects-for-the-rest-of-us/)
