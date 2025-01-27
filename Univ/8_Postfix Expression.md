## 식 계산
1. infix(중위 표기법): `피연산자` `연산자` `피연산자`

    eg) a+b
2. postfix(후위 표기법): `피연산자` `피연산자` `연산자`

    eg) ab+

3. prefix(전위 표기법): `연산자` `피연산자` `피연산자`

    eg) +ab


#### 연산자 우선순위
```
1. `()`
2. `^`
3. `*`, `/`, `%`
4. `+`, `-`
```

### 전위 표기법(중위->후위)
#### ex)

`a+b` --> `ab+`

`a*b+c` --> `ab*c+`

`a+b*c` --> `abc*+`

`a+b*c-d` --> `abc*+d-`

---

`b*c-d*a` --> `bc*da*-`

`a-b*c-d` --> `abc*-d-`

`a+b+c` --> `ab+c+` or `abc++`

`a+b*c/d^2` --> `abc*d2^/+`

`(1+2)*7` --> `12+7*`

---

`a*b*c` --> `abc**` or `ab*c*`

`a*b/c` --> `ab*c/`

`a*(b+c)/d-g` --> `abc+*d/g-`

`a/b-c+d*e-a*c` --> `ab/c-de*+ac*-`

#### 알고리즘
- 피연산자를 만나면 그대로 `출력`

- 연산자를 만나면 스택의 top에 있는 연산자와 우선순위 비교

    - 스택의 top 연산자보다 우선순위가 높으면 `push`

    - 그렇지 않으면 스택의 top을 `pop하여 출력`(반복)

#### 괄호 ()가 있는 경우
- 괄호의 처리: 괄호 자체는 출력하지 않음

    - `왼쪽 괄호`는 무조건 `push`

    > 스택에 있을 때는 우선 순위가 가장 낮은 것으로 간주(즉, 이후에 나오는 연산자는 반드시 push 됨)

    - `오른쪽 괄호`가 나오면 스택에서 왼쪽 괄호가 나올 때까지 `pop하여 출력`