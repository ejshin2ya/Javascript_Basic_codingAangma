## 1강. 변수

- 자바스크립트에서 변수를 선언할 때 변하지 않는 값은 const, 변할 수 있는 값은 let으로 선언하세요.
- 변수의 특징

1. 변수는 문자와 숫자, $와 \_만 사용
2. 첫글자는 숫자가 될 수 없습니다.
3. 예약어는 사용할 수 없습니다. (ex:`let let=99;`)
4. 가급적 상수는 대문자로 알려주세요.
5. 변수명은 읽기 쉽고 이해할 수 있게 선언

## 2강. 자료형

1. 문자형(String)

- "", ``,'' 큰따옴표, 작은따옴표, 백틱으로 문자열 만들수 있다.

```
 const name = "Mike"; //문자형 String
      const age = 30;
      const name1 = "Mike";
      const name2 = "Mike";
      const name3 = `Mike`;
```

- 작은 따옴표로 문자열을 만들때 작은따옴표 앞에 \를 넣으면 특수문자로 인식해준다.
  `const message2 = "I\'m a boy.";`
- 백틱은 문자열 내부를 변수로 표현해줄떄 사용
  `` const message3 = `My name is ${name}`; ``
- 바로 표현식을 넣어서 사용도 가능
  `` const message4 = `나는 ${30 + 1}살 입니다.`; ``

2. 숫자형(Number)

- 소수점 표현과 사칙연산 가능

```const age = 30; //숫자형 Number
      const PI = 3.14;

      console.log(1 + 2); //더하기
      console.log(10 - 3); //빼기
      console.log(3 * 2); //곱하기
      console.log(6 / 3); //나누기
      console.log(6 % 4); // 나머지
```

> 숫자를 숫자 0으로 나누면 어떤 값이 나올까?

- Infinity가 나온다.

```const x =1/0; //??
    console.log(x) //Infinity
```

> 문자열을 숫자 0으로 나누면 어떻게 될까?

- NaN이 나온다.(Not a number)

```
      const name ="Mike";
      const y=name/2;
      console.log(y) //NaN= Not a number
```

3. Boolean

```
   const a= true;//참
   const b=false; //거짓

    const name="Mike";
    const age=30;
    console.log(name=="Mike")//true
    console.log(age>40)//false
```

4. null과 undefined

- null은 존재하지 않는 값을 뜻하고, undefined는 값이 할당되지 않았음을 뜻한다.

```
let age;
console.log(age);

let use =null;
```

//객체형, 심볼형

5. typeof 연산자

- 변수의 자료형을 알 수 있다.

```
const name="Mike";

console.log(typeof 3); //number
console.log(typeof name);  //string
console.log(typeof true);  //boolean
console.log(typeof "xxx");  //string
console.log(typeof null);  //object
console.log(typeof undefined);  //undefined
```

- typeof null은 object형으로 나오는데, "object"는 객체형을 뜻한다. 우선, null은 객체가 아니다. 자바스크립트 초기 버전의 오류에 해당한다.

6. 기타

- 백틱을 사용하지 않고 "" 일반따옴표를 사용해 문자열 내부에 변수를 만들면 변수명이 그대로 노출되니 주의해주세요.

```
const message2="My name is ${name}";
console.log(message2) //"My name is ${name}"
```

- 문자형 + 문자형 = 문자형

```
const name="Mike";
const a="나는";
const b=" 입니다.";
console.log(a+name+b);//"나는 Mike 입니다."
```

- 숫자형 + 문자형 = 문자형

```
const name="Mike";
const a="나는 ";
const b=" 입니다.";
const age=30;//number
console.log(a+age+"살"+b);//"나는 30살 입니다."
```

## 3강. alert, prompt, confirm

- alert : 알려줌
- propmt : 입력받음
- confirm : 확인 받음

1. alert()

- 메세지를 띄워주는, 일방적으로 알리는 용도
- 비밀번호 틀렸습니다 등등

2. prompt()

- 사용자에게 어떤 값을 입력 받을 떄 사용

```
const name=prompt("이름을 입력하세요.");
//alert("환영합니다,"+name+"님");
alert(`안녕하세요 ${name}님`);
```

- 입력창에 값을 넣지 않고 취소 누르면 null값이 입력
- prompt는 default 값을 입력할 수 있다.
- prompt는 두개의 인수를 받을 수있으며, 첫번째 값은 메세지, 두번쨰 값은 입력받을 default값이 된다.
  `const name = prompt("예약일을 입력해주세요.","2020-10-");`

3. confirm()

- 확인받을 때 사용
- 확인버튼 누르면 true, 취소버튼 누르면 false값이 들어온다.

* 결제 하시겠습니까? 정말 삭제하시겠습니까? 사용자의 확인을 받을때 사용.

```
    const isAdult =confirm("당신은 성인 입니까?");
    console.log(isAdult)
```

4. 기본 제공되는 창들의 단점

- 창을 닫기 전에는 스크립트 일시 정지
- 스타일링이 불가능하다. 위치, 모양 바꿀 수 없다. 보통 모달을 많이 사용한다.

* 간편하고 빠르다는 장점도 있다.

## 4강. 형변환

- String => 문자형으로 변환
- Number() => 숫자형으로 변환
- Boolean() => 불린형으로 변환

- 자료형이 다르면 의도치한 결과를 불러 일으킬때가 있어서 형변환이 필요하다.

* prompt 입력값은 문자형이기 때문에 수학점수와 영어점수를 덧셈(+) 문자형으로 출력된다.

```
      const mathScore = prompt("수학 몇점?");
      const engScore = prompt("영어 몇점?");
      const result = (mathScore + engScore) / 2;
      console.log(result);
```

- 반면에 덧셈이 아닌 나눗셈은 자동형변환 기능이 있어서 문자형 자료를 숫자로 나눠주는 특징이 있다.

```
"9080" / 2; // 4540
"6"/"2" =3; //자동 형변환
```

- 자동형변환은 원인을 찾기 어려운 경우가 많으므로 명시적 형변환을 해줘야한다.

* String() :괄호안의 값을 문자열로 바꿔준다.

```
      console.log(
        String(3),
        String(true),
        String(false),
        String(null),
        String(undefined)
      );
      //3 true false null undefined
```

- Number() : 괄호안의 값을 숫자로 바꿔준다.
- 괄호안에 문자형이 있을때는 NaN이 나오므로 주의

```
      console.log(
          Number("1234"),
          Number("abcd"),
          Number(true),
          Number(false)
          );
    //1234 NaN 1 0
```

- Boolean() : false에 대해서만 알면 된다. 그외는 true 반환
- Boolean()이 false를 반환하는 경우

1. 숫자 0
2. 빈문자열 ""
3. null
4. undefined
5. NaN

```
      console.log(
        Boolean(0),
        Boolean(""),
        Boolean(null),
        Boolean(NaN),
        Boolean(undefined)
      );
      //false false false false false
```

> 주의 사항

- Number(null) => 0을 반환
- Number(undefined) => NaN을 반환
- 사용자가 확인창에서 취소 버튼을 누르면 null값이 들어오게 되고 이를 숫자로 바꾸면 0으로 반환된다.

> 주의사항 2

- Boolean(0) => false
- Boolean("0") => true
- Boolean('') => false
- Boolean(' ') => true(공백이 있기 때문)
