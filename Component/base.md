# Base

* GameObject : 게임을 구성하는 기본요소이다.  
* Empty GameObject : 다른 객체를 자식으로 두기 위해 사용하며, Transform 컴포넌트만 가지고 있다. 화면에는 보이지않는다.  
* Package : 유니티 기능이나 애셋을 모아놓은 것이다.  

* Rigidbody - 중력의 영향을 주는 컴포넌트
  * Mass - 충돌했을 때 영향을 주는 정도 (무게)
  * Use Gravity - 중력 여부
  * Is Kinematic - 외부 물리 효과 적용 여부
  
* Collider - 물리효과를 주는 컴포넌트

* Material - 재질
  * metalic  - 금속 재질 수치
  * Smoothness - 빛 반사 수치
  * Albedo - 색상 / 이미지도 드래그앤드랍으로 삽입 가능(Texture)
  * Emission - 텍스쳐 밝기 조절
  * Tiling - 텍스쳐 반복 타일 개수
  * Physics Material - 탄성과 마찰을 다루는 물리적인 재질 
    * Bounciness - 탄성력
    * Friction - 마찰력
    * Bounciness Combine - 다음 탄성을 계산하는 방식 (최대로)
    * Friction Combine - 다음 마찰력을 계산하는 방식 (최소로)
    
### 물체 필수 요소
1. Mesh
2. Material
3. Collider
4. RigidBody
    

