# Base

게임 오브젝트 -> 컴포넌트 -> 

## GameObject  
- 게임을 구성하는 기본요소   
- Empty GameObject : 다른 객체를 자식으로 두기 위해 사용하며, Transform 컴포넌트만 가지고 있다. 화면에는 보이지않는다.  

## Component  
- 게임오브젝트는 1개 이상의 컴포넌트로 구성된다  
- 모든 게임오브젝트는 반드시 Transform 컴포넌트를 가진다
- Transform 컴포넌트 : 게임오브젝트의 3차원 공간에서의 위치, 방향, 크기를 결정
- Rigidbody도 컴포넌트임

## 패키지 매니저  
- 패키지(package) : 유니티 기능이나 애셋을 모아놓은 것  

## Rigidbody 
- 중력의 영향을 주는 컴포넌트
  * Mass - 충돌했을 때 영향을 주는 정도 (무게)
  * Use Gravity - 중력 여부
  * Is Kinematic - 외부 물리 효과 적용 여부
  
## Property(속성)  
- 컴포넌트는 여러가지 속성으로 구성된다
- Game : 1개 이상의  Scene으로 구성
- Scene : 여러개의 GameObject로 구성
- GameObject : 1개 이상의 Component로 구성
- Component : 1개 이상의 Property로 구성
  
## Collider  
- 물리효과를 주는 컴포넌트

## Material  
- 게임오브젝트의 표면 재질을 결정한다
- 컴포넌트이자 애셋이다

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
    
## Texture
- 정식명칭은 texture map이며, material에서 사용하는 이미지 파일이다.  

## Physic Material(물리 재질, 물리 머티리얼)  
- 물리 시뮬레이션을 위한 세부 속성 변경  
- 마찰과 탄성을 조정 가능

## Prefab(프리팹)  
- 게임오브젝트 생성을 위한 템플릿 역할을 하는 에셋(파일로 존재)
- 인스턴스(instance) : 씬에 생성된 게임오브젝트
- 프리팹으로부터 인스턴스 생성 : 에셋으로 존재하는 게임오브젝트를 복제하여 씬에 생성
- 프리팹을 변경하면 프로팹으로부터 생성된 모든 인스턴스에도 적용됨
- 속성 변경시 “Auto Save” 체크  

### Prefab override
- 프리팹으로부터 생성된 인스턴스의 속성을 변경
- 프리팹으로부터 물려받은 값을 무시하고 덮어쓰는 동작
  - “Open” 버튼 : 프리팹 (편집) 모드로 전환됨, Alt 키를 누른채 클릭하면 프리팹만 편집하는 모드로 전환됨
  - “Select” 버튼 : 이 게임오브젝트를 생성할 때 사용한 프리팹을 찾아줌
    - Project 창에서 해당 프리팹이 선택됨 
  - “Overrides” 버튼 : 프리팹으로부터 물려받은 속성 중에 “오버라이드"한 속성을 표시함
    - 속성 중에 : 위치(Position)와 방향(Rotation)은 해당하지 않음
    
### Prefab variant
- 기존 프리팹으로부터 파생된 프리팹으로, 상속 개념과 비슷하다

    
## 유니티 왼손 좌표계 ( Left_Handed Coordinate System )  
![Untitled](https://user-images.githubusercontent.com/80669633/223623193-150effb1-6aca-4dfa-8fc8-cd28e9d4cc80.png)
엄지 손가락(+X), 검지 손가락(+Y), 중지 손가락(+Z)

- Local : 오브젝트 중심의 좌표계  
- World : 월드 중심의 좌표계  
  
- CW (Clock_Wise) : 시계방향  
- CCW (Count Clock_Wise) : 반시계방향  
      
- Unity : Y-UP Left Hand  
- Unreal : Z-UP Left Hand  
    
## Camera
- 마우스 우클릭 + WASD/QE
- 특정 게임오브젝트 포커스(더블클릭 or 선택후 ‘F’ 키 → Alt키를 누른 채 마우스 좌클릭/드래그
- Main Camera에서 마우스 우클릭 → Align With View (단축키: Ctrl+Shift+F)
    
    
### 물체 필수 요소
1. Mesh
2. Material
3. Collider
4. RigidBody  

- DirectionalLight : 방향이 중요한 주 광원

- normalizedTime : 정규화된 시간. 무조건 시작은 0 , 끝은 1
///////////////////////
2단점프
1. 2단 점프 변수선언 public float doubleJumpForce = 400.0f;
2. 2번이니까 부울로 1단점픈지 2단점픈지 판별 public bool doubleJumpeUsed = false;
3. 조건 붙여서  else if (Input.GetKeyDown(KeyCode.Space)&&!isOnGround && !doubleJumpeUsed)
        {
            doubleJumpeUsed = true;
        }

dash
1. 대쉬 변수. 부울
2. 애니메이터에서 실수형 파라미터 하나 추가
3. 대쉬모드일경우 스피드 2
