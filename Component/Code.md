
GetComponent<T> : 자신의 T타입 컴포넌트를 가져옴.
velocity : 현재 이동속도 Vector3 사용
Rigidbody 관련 코드는 FixedUpdate에서 사용
  
  
* 컴포넌트 가져오기
  **선언 -> 초기화 -> 호출**
  ```
  Rigidbody rigid;
  rigid = GetVomponent<Rigidbody>();
  ```
  
* 물체 속도를 설정해서 움직이기
  ```C++
  Rigidbody rigid;
  rigid.velocity = new Vector3(2,4,-1);               // velocity를 이용한다.
  ```
  
  * 힘으로 움직이기
  ```
  
  ```

  
 # AddForce   
  
1. Force.Force : 매개변수를 임펄스(N/s)로 해석하고 Force* dt/m

2. Force.Impulse : N/s 해석, Force / m 
  
-> 보통 델타타임이 0.02이니 impulse는 forse의 50배라고 생각하면됨.
 
  EX)
  
  1. playerRb.AddForce(Vector3.up * 50,ForceMode.Impulse);
  
  2. playerRb.AddForce(Vector3.up * 500,ForceMode.Force);
  
  코드에 포함되어있는 상수값 : Literal
  
  이때 리터럴 사용은 최소화하는게 좋은 코드
  
  
 유니티 변수 직렬화  
  1. 에디터에서 값을 변경
  2. 에디터에서 값을 관찰
  
  C# 의 [] : 어트리뷰트
  -> 바로 다음 줄에 나오는 클래스/메서드/변수에 특성 부여
  
  [Header(" ")]
  
  Object 라는 최상의 클래스로부터 Instantiate로 복제 가능  
  Prefab : 에셋(파일->보조 기억장치인 하드디스크)으로 저장한 게임오브젝트  
  Instance ( V : Instantiate ) : 개체, 구체화된것, 게임 씬에 실제로 존재하는 것, 메모리에 존재하는 것  

  C# Methods
  - Instance Method : 객체가 있어야 호출이 가능하다 (박스 모양)
  객체에 속해있는 값을 가지고 처리한다.
  - Static Method : 객체가 없어도 클래스로 호출이 가능하다.  
  
  C++ Template -> C # Generic  
  
  Invoke
  InvokeRepeating
  
  Asset 선택 -> Inspector창에 Import Setting이 표시
  
  클래스 계층구조  
  자식 - - -> 부모 : is a 관계
  
  자식 is a 부모 클래스 (O)  
  부모 is a 자식 클래스 (X)  
  
  게임 오브젝트 찾기
  GameObject.Find("Player").GetComponent<PlayerController>();
 
  ## corountine (코루틴)
  병렬로 처리해서 동시 일 처리가 가능하다.  
  IEnumerator를 자료형으로 코루틴 함수를 만든다.   
  yield : return 앞에 붙이고 cpu를 양보해서 먼저 처리하도록 한다.
    - WaitWhile  
  
  StartCoroutine
  StopCoroutine
  
  ### Fade() 함수
  
  #### learp = Linear Interpolation(선형 보간, 1차 함수)  
  보간 공식 : (1-t)s + t * e   
  - > S + t(E - S)
  
  Vector3.Lerp(시작값,끝값,0이면 파라미터1이고 1이면 파라미터 2 / 0.5라면 중간값이 나오겠지)
  
  sensitivity :
  drag :  평행이동에서의 항력
  angular drag : 회전에서의 항

  Inter polate (보간) : A, B 중간값
  extra polate (외삽) : A, B 바깥 쪽 
  
  Collision Detection : 세세하게 충돌검사를 하는 정도  
  
    
  - Time.time : 게임 시작된 이후의 시간  
  - Time.Scale :  

  <hr/>
  
  # 12주차
  
  GameObject.Find("부모게임오브젝트/자식게임오브젝트") 으로 중복된 게임 오브젝트도 쉽게 찾을 수 있다.  // /는 부모없는 게임오브젝트 찾음
  이렇게 할 경우 속도 향상에 도움이 된다.  
  
  리지드바디는 fixedupdate 에서 하는게 좋다.  
  
  ### VSync : 컴퓨터 디스플레이에서 그래픽 카드의 프레임 생성과 모니터의 프레임 출력 타이밍을 맞추도록(동기화) 하는 설정  
  
  Physic Material  
  - Friction Comnine
    - Multiply
  
  - OnTrigger  
  다른 오브젝트와 충돌한 정보만  
  - OnCollision  
  충돌한 지점의 정보  
  
 - collision : 충돌에 관한 정보를 가진다. 컴포넌트가 아니고 클래스다.
 - collider : 충돌 대상을 나타낸다. 컴포넌트의 역할을 한다.  
  
  컴포넌트는 게임오브젝트의 대리자 역할을 한다.  
  this.transform -> this.gameObject.transform -> this.gameObject.GetComponent<Rigidbody> // 마지막 맞는지 몰겟음  
  
  ### string Interpolation : 문자열 보간  
  $"문자열 {변수}로 한 번에 가능하다.";  
  
  # 6주차
  
  - 속력 : 크기 -> 스칼라(float, int) -> speed  
  - 속도 : 크기, 방향 -> 벡터(vector3) -> velocity  
  
  C#  
  - Pascal : 클래스, 메서드, 프로퍼티(C#표준)-> Rigidbody  
  - Camel : 변수, 프로퍼티(유니티) -> rigidBody  
  - Snake : MAX_NUM(static 변수, const, ...)  
  
  Unreal : Pascal(클래스, 함수, 변수)  
  C++ 변수 : Carmel  
  C 변수 : Snake  
  
  
