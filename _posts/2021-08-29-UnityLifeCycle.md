---
title:  "유니티 Life Cycle"
excerpt: "유니티 Life Cycle에 대해 알아보자~ "

categories:
  - Unity
tags:
  - [Unity]

toc: true
toc_sticky: true
 
date: 2021-08-29
last_modified_at: 2021-08-29

---

###### 1️⃣ 초기화 영역

- **Awake()**

  게임 오브젝트 생성할때, 최초 실행

  ```c#
  void Awake(){
      Debug.Log("플레이어 데이터가 준비되었습니다.")
  }
  ```

  

- **Start()**

  업데이트 시작 직전, 최초 실행

  ```c#
  void Start(){
      Debug.Log("사냥 장비를 챙겼습니다.")
  }
  ```



###### 2️⃣활성화 영역

- **OnEnable()**

  게임 오브젝트가 활성화 되었을때, 최초 1회 실행이 아닌 켜고 끄고 할때마다 실행

  ```c#
  void OnEnable(){
      Debug.Log("플레이어가 로그인 했습니다.")
  }
  ```

  

######  3️⃣물리 연산 영역

- **FixedUpdate()**

  물리 연산 업데이트, 유니티 엔진이 물리연산을 하기전에 실행되는 함수, 

  CPU 많이 사용, 1초에약 50회 호출

  ```c#
  void FixedUpdate(){
      Debug.Log("이동~")
  }
  ```

  

###### 4️⃣게임 로직 영역

- **Update()**

  게임 로직 업데이트, 물리연산에 관련된 로직을 제외한 주기적으로 변하는 로직을 넣을때 사용함,

  환경에따라 실행주기가 떨어질수있음, 1초에 약 60회 호출

  ```c#
  void Update(){
      Debug.Log("몬스터 사냥!!")
  }
  ```

  

- **LateUpdate()**

  모든 업데이트 영역에  로직들의 실행이 끝난뒤에 호출되는 함수

  ex) 캐릭터를 따라가는 카메라, 로직의 후처리 등...void 

  ```c#
  void LateUpdate(){
      Debug.Log("경험치 획득.")
  }
  ```



###### 5️⃣비활성화 영역

- **OnDisable()**

  게임 오브젝트를 활성화 상태에서 비활성화 상태로 바뀔때 실행되는 함수

  비활성화되면 업데이트 들의 실행이 멈춘다

  ```c#
  void OnDisable(){
      Debug.Log("플레이어가 로그아웃 했습니다")
  }
  ```

  

###### 6️⃣해체

- **OnDestroy()**

  게임 오브젝트가 삭제 될 때,

  오브젝트가 삭제가 되기 직전에 무언가 남기고 삭제된다는 의미 Awake랑 반대의미 일수도 있다.

  ex) 스크립트가 들어있는 오브젝트를 삭제하면 콘솔창에 입력이 된다

  ```c#
  void OnDestroy(){
      Debug.Log("플레이어 데이터를 해제 하였습니다")
  }
  ```

  **<u>개인 공부용 블로그 이므로, 틀린사항이 있을수 있습니다😅</u>**
{: .notice--primary} 


