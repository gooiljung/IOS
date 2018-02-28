## Swift

**자료형과 상수**
 
 - let : 상수 초기화를 한후에 값을 바꿀 수 없다.
 - var : 모든 자료형을 넣을 수 있다.
 
 ```
 let pi = 3.14
 var message: String
 var abc: Int
 var bool = false
 var weight: Double = 65.5
 ```
 이렇게 타입이 정해지면 다른 타입으로 바꿀 수 없다.
 
 - Core Data : 데이터를 저장할수있는 프레임워크
 - action : 메소드를 생성한다 
 - outlet : property를 생성한다 
 - optional 은 enum 이다 
 - swift 에서 지원하는 function인 루트 cos 이런것들을 그냥 다른 타입처럼 받을 수 있다
 

```
Operation.aaa(sqrt)

Operation.aaa(let function)
something = function(something)
```

Struct 와 Enum 은 값으로 전달되고 상속이 불가 하고 Class 는 참조 형식으로 전달된다.

클래스에는 자동으로 초기화하는 생성자가 있고
구조체안에서는 자동 생성되는 초기화 함수는 구조체안에 있는 모든 변수를 입력인자로 갖게된다.

## Optional 

optional 은 제네릭 같은거고 enum 이다

```
enum Optional<T>{
	case None
	case Some(T)
}

let x: String? = nil
->곧 optional<String>.None
let x: String? = "hello"
var y = X!
-> 곧
switch x {
	case Some(let value):y = value
	case None; //raise an exception
}
```

?을 사용하면 추출할 수 있다면 추출을 해나가고 없으면 nil 을 반환한다.

옵셔널은 연결되서 사용되어질 수 있다.

```
let s: String? = .... 
display.text = s ?? " "
```
이것의 뜻은 s가 nil이 아니라면 S를 집어넣고 nil이면 빈칸을 넣어준다.


## Tuples

타입이 존재하면 뭐든지 tuple 로 만들 수 있다. 리턴 타입을 튜플로 할 수 도있다.

```
let x: (String,Int,Double) = ("hello", 5, 0.85)
let (word, number, value) = x
print(word)  // "hello"
print(number) // "5"
print(value) // 0.85


let x: (w: String,i: Int,v: Doule) = ("hello", 5, 0.85)
print(x.w) // 위랑 같은 결과
print(x.i)
print(x.v)


```

swift 에서는 _ 의미가 그곳은 무시한다는 의미인데 튜플에서 어느 특정값은 쓰고 싶지않으면 _ 를 붙이면 된다.

```
let x : (String, Double, Int) = ("d", 2.0, 1)
let (word, _ , id) = x
print(id)
print(word)
```
## 구조 

**Class, Enum, Struct** 

- 모두 프로퍼티와 함수를 가질 수 있다. 단 Enum 은 저장 프로퍼티를 가질 수 없다. 하지만 계산 프로퍼티를 가질 수 잇는데 enum 이 기억하고 있는 저장소는 case 다. 
- 모두 초기화함수를 가질 수 있다. (생성자)
- 상속은 Class에서만 할 수 있다.
- Value type 은 Struct, Enum
- Reference type 은 Class (힙 메모리) 자바와는 다르게 가비지 콜렉션이 있는게 아니라 reference 받는 횟수를 카운트해서 카운트한 값이 0 이되면 그때 힙 메모리에서 제거된다.


## function ,property

```
func calcul (a k1: Double, b k2: Double)-> Double{
    return k1+k2
    
}
print(calcul( a : 3 , b : 5))

```

a, b 는 외부에서(external) 사용하고 k1, k2 는 내부에서(internal) 사용한다 . 외부 이름을 _ 할 경우에 calcul(3,5) 로 호출 가능하고 외부이름을 사용안하면 호출할때 내부이름 사용해서 호출하고 첫번째 파라미터의 외부이름을 default 로 하면 _ 이고 두번째 파라미터부터는 내부이름이다.

**Method Override** 는 func 앞에 override를 붙여주면 된다. 단 메소드에final 이 붙여있으면 override 불가능.
class 에 final  붙으면 상속불가.

















