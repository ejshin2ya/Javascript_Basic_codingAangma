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

## 5. 연산자

> 나머지를(%) 어디에 쓸까?

- 홀수 : X%2=1
- 짝수 : Y%2=0
- 5보다 작은 수를 얻고 싶으면 X%5 =0~4사이의 값만 반환

> 거듭제곱

```
const num = 2*3;
console.log(num); //8
```

> 연산자 줄여쓰기

```
let num=10;
num %= 5;
num +=5;
num *=5;
num -=5;
```

> 증가 연산자, 감소 연산자

```
num ++
num --
```

- ++를 앞에적어줘서 증가된 값이 변수에 담긴다. ++를 뒤에 적으면 증가되기 전의 값이 변수에 담긴다.

## 6.비교 연산자

- 동등연산자(==)보다 일치연산자(===)를 사용해야함
- 일치연산자는 타입까지 비교를 해주기 때문에 버그를 잡아준다.

```
      console.log(10 > 5);
      console.log(10 == 5); //동등 연산자
      console.log(10 != 5);

      const a = 1;
      const b = "!";
      console.log(a === b); //일치연산자
```

> if, else, else if

```
const age = 30;
      if (age > 19) {
        console.log("환영 합니다.");
      } else {
        console.log("안녕히 가세요.");
      }
```

## 7. 논리 연산자

1. ||(OR)

- 여러개 중 하나라도 true이면 true
- 즉, 모든 값이 false일때만 false를 반환

2. &&(AND)

- 모든값이 true이면 true
- 즉, 하나라도 false이면 false를 반환

3. !(Not)

- true면 false, false면 true

4. 평가

- OR는 첫번째 true를 발견하는 즉시 평가를 멈춤.
- AND는 첫번째 false를 발견하는 즉시 평가를 멈춤

* 성능 최적화를 위해 가능성이 적은 조건을 앞에다가 적어준다.

5. 우선순위
   > 남자이고, 이름이 Mike이거나 성인이면 통과하는 조건식만듬

```
      const gender = "F";
      const name = "Jane";
      const isAdult = "true";

      if ((gender === "M" && name === "Mike") || isAdult) {
        console.log("통과");
      } else {
        console.log("돌아가.");
      }
```

> 결과는? 통과

- 남자도 아니고 이름이 Mike도 아니지만 우선순위에 의해서 && 연산자가 먼저 실행되고 뒤에 있는 || 연산자는 true이기 떄문에 true를 반환하는 상황 발생

> 의도한 바를 만들기 위해서 조건문의 괄호를 바꿔줘야한다.

```
      if (gender === "M" && (name === "Mike" || isAdult)) {
        console.log("통과");
      } else {
        console.log("돌아가.");
      }
```

## 8. 반복문

- for문, while, do~while문이 있다.
- do~while은 적어도 한번은 실행하는 차이점이 있다.
- break 멈추고 빠져나옴
- continue 멈추고 다음 반복을 진행
- 횟수가 정해져있으면 for문사용, 아니면 while을 사용
- do while문은 거의 사용 안함

```
      //contiue
      //짝수만
      for (let i = 0; i < 10; i++) {
        if (i % 2) {
          continue;
        }
        console.log(i);
      }
```

## 9. switch문

- switch문에서는 break를 조건마다 작성해줘야한다.

```
switch(평가){
    case A:
    //A일때 코드
    break;
    case B:
    //B일때 코드
    break;
}

if(평가==A){
    //A일때 코드
}else if(평가==B){
    //B일때 코드
}
```

- 조건과 일치 하지 않는 값을 입력하면 default 값을 반환

```
      let fruit = prompt("무슨 과일을 사고 싶나요?");
      switch (fruit) {
        case "사과":
          console.log("100원 입니다.");
          break;
        case "바나나":
          console.log("200원 입니다.");
          break;
        case "키위":
          console.log("300원 입니다.");
          break;
        case "멜론":
        case "수박":
          console.log("500원 입니다.");
          break;
        default:
          console.log("그런 과일은 없습니다.");
      }
```

## 10. 함수의 기초

- 매개변수가 있는 함수에 매개변수가 없이 입력되면 undefined값이 들어가게 되어 조건문에서 false를 반환하여 false에 해당하는 조건을 실행하게 된다.

```
      function sayHello(name) {
        let msg = "Hello";
        if (name) {
          msg += `, ${name}`;
        }
        console.log(msg);
      }
      sayHello();
      sayHello("Mike");
    </script>
```

- 함수안에 들어있는 let 변수는 함수밖에서 인식이 안된다.
- 전역변수는 어디에서나 접근 가능한 변수
- 지역변수는 함수 내부에서만 접근 가능한 변수

```
    let msg = "Hello"; //전역 변수 (global varable)
    console.log('함수 호출 전')
    console.log(msg)

    function sayHello(name) {
        if (name) {
          msg += `, ${name}`;
        }
        //지역 변수(local varable)
        console.log(msg);
      }
      sayHello("Mike");
      console.log('함수 호출 후')
      console.log(msg)

      //index.html:200 함수 호출 전
index.html:201 Hello
index.html:207 Hello, Mike
index.html:210 함수 호출 후
index.html:211 Hello, Mike
```

- let은 동일한 이름으로 선언될 수 없지만 함수 내부와 밖에서는 동일하게 사용가능

```
 let msg = "welcome"; //전역 변수 (global varable)
    console.log(msg)

    function sayHello(name) {
        //지역 변수(local varable)
        let msg="Hello"
        console.log(msg+" "+name);
      }
      sayHello("Mike");
      console.log(msg)
```

- or연산자 활용
- 매개변수가 있는 함수에 매개변수를 전달하지 않으면 undefined가 반환이 되어야 하는데, 여기서는 or연산자를 사용하여 name이 false일때 뒤에 값이 true가 되면서 friend가 newName에 입력이 된다.

```
    function sayHello(name){
        let newName = name || "friend";
        let msg =`Hello, ${newName}`
        console.log(msg);
    }
    sayHello();
    sayHello('Jane');
```

- 매개변수가 입력되지 않았을때 default값을 설정해놓으면 설정된 값이 입력된다.

```
    function sayHello(name='friend'){
        let msg =`Hello, ${newName}`
        console.log(msg);
    }
```

- return으로 값 반환
- 반환값 없는 함수와 return 오른쪽에 값이 없는 함수는 undefined를 반환한다.
- return오른쪽에 값이 없는 경우는 함수를 종료하려는 목적으로 사용하기도 한다.

```
    function showError(){
       alert('에러가 발생했습니다.');
       return;
   }
   const result=showError();
   console.log(result);
```

- 함수(function) 만들기 Tip

1. 한번에 한작업을 집중
2. 읽기 쉽고 어떤 동작인지 알 수 있게 네이밍

- showError //에러를 보여줌
- getName //이름을 얻어옴
- createUserData //유저데이터 생성
- checkLogin //로그인 여부 체크

## 11. 함수 표현식, 화살표 함수

> 함수 선언문 vs 함수 표현식

- 함수선언문은 어디서든 호출 가능(호이스팅)

```
sayHello();
function sayHello(){
    console.log('Hello')
}
```

- 함수 표현식은 순서대로 코드작성

```
let sayHello=function(){
    console.log('Hello')
}
sayHello();
```

> 화살표 함수

```
let sayHello =()=>{
    console.log('Hello')
}
```

- return문이 한줄일 때는 중괄호 지우고 return도 생략가능

```
const add = (num1, num2) => num1+num2;
```

- 화살표함수는 Es6이후로 활발히 사용됨으로 익숙해지면 좋다.

## 12. 객체(object)

- 객체 안의 마지막 쉼표는 수정, 삭제에 용이하므로 그냥 두는 것이 좋다.

```
const superman={
    name:'clark',
    age:33,
}
```

- 접근

```
superman.name //'clark'
superman['age'] //33
```

- 추가

```
superman.gender='male';
superman['hairColor']='black';
```

- 삭제

```
delete superman.hairColor;
```

- age가 없는 객체를 입력했을때도 함수가 true를 반환하는 것을 방지하기 위해 'age' in user를 사용한다.

```
    function isAdult(user){
        if(!('age' in user) || user.age <20){
            return false;
        }
        return true;
    }
    const Mike={
        name : "Mike",
        age: 30,
    }
    const Jane= {
        name:"Jane",
    }
    console.log(isAdult(Jane))  //false 반환
```

- 객체 for...in
- 객체의 key를 꺼낼 수 있다.

```
const Mike ={
    name:"Mike",
    age:30
};

for(x in Mike){
    console.log(Mike[x]) //Mike['age]
}
// "Mike", 30
```
