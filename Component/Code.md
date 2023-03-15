
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

  
  AddForce   
  
  Force.Force : 매개변수를 임펄스(N/s)로 해석하고 Force* dt/m

Force.Impulse : N/s 해석, Force / m 
  
 보통 델타타임이 0.02이니 impulse는 forse의 50배라고 생각하면됨.
 
  EX)
  
  playerRb.AddForce(Vector3.up * 50,ForceMode.Impulse);
  
  playerRb.AddForce(Vector3.up * 500,ForceMode.Force);
  
  코드에 포함되어있는 상수값 : Literal
  
  이때 리터럴 사용은 최소화하는게 좋은 코드
  
  
 유니티 변수 직렬화  
  1. 에디터에서 값을 변경
  2. 에디터에서 값을 관찰
  
  C# 의 [] : 어트리뷰트
  -> 바로 다음 줄에 나오는 클래스/메서드/변수에 특성 부여
  
  [Header(" ")]
  
  Original Prefab
  Prefab Varient
