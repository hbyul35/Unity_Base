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
