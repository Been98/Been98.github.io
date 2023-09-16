---
title : "[유데미x스나이퍼팩토리] 10주 완성 프로젝트 캠프 - 유니티(Unity) 기초 학습 1주차"
excerpt : "학습일지"

categories:
    - Udemy
    - Unity
    - 스나이퍼팩토리
    - 부트캠프
tags:
    - Udemy
    - Unity
    - 스나이퍼팩토리
    - 부트캠프
last_modified_at : 2023-09-17
---

유데미 x 스나이퍼팩토리 10주 완성 프로젝트 캠프 - 유니티 기초 학습 1주차 내용이다.
매 주 월, 수, 금 수업을 진행하고 있으며 첫 수업으로는 클라이언트 개발자의 간단한 설명과 각 종 엔진에 관하여 설명을 해 주었으며 또 유니티 설치와 프로젝트 생성 설명과 유니티 기능에 대하여 설명을 진행했다. 유니티가 처음은 아닌지라 간단한 예제정도는 충분히 수행할 수 있었다.

수요일 수업 
수요일은 flappy bird를 간단하게 만들어보는 시간을 가졌다.
![images](https://github.com/Been98/Been98.github.io/assets/85021523/6954fd59-1c07-4045-8482-73c915b63dc3){: .align-center} (대충 이런 게임)
수업을 진행하며 차근차근 게임을 완성시켰고 완성 후 코드로 설명을 붙혀나가겠다.
'Player.cs'
{: .notice--primary} 
![image](https://github.com/Been98/Been98.github.io/assets/85021523/5b231fbd-7a98-4e9a-9b21-867e88099022){: .align-center}
간략하게 해당 스크립트를 해석하자면 플레이어는 현재 y포지션의 값이 lowWarn보다 낮으면 
jumpPower * jumpBoost값 만큼 이동한다. 낮지 않을 시 jumpPower만큼 이동한다.
여기서 이동함수에 대해 좀 더 알아보자
간단한 이동으로는 물체의 position을 변경해 물체를 이동하는 방법이 있지만 이는 순간이동을 하는 느낌을 주기 때문에 움직이는 물체라고 보기는 어렵다고 생각한다.
다른 이동 함수에는 Translate, MoveTowards함수가 있다.
'Translate'는 '방향'이라는 인자값을 받아서 그 방향대로 계속 이동하는 역할을 합니다.

'MoveTowards'는 '현재위치'에서 '목표'를 향하여 이동하는 역할을 합니다.

허나 이 둘은 물리적 충동은 고려되지 않고 단순한 위치값을 이용한 이동이다. 

물리적 속성을 가지게 만드는 RigidBody를 활용한 이동으로 AddForce와 velocity가 있다.
'AddForce'는 Rigidbody에 힘을 가해 '가속도'를 줍니다.
AddForce의 매개변수로 ForceMode를 지정할 수 있는데 종류는 4가지가 있다.
-ForceMode.Force - Default값으로 오브젝트의 질량을 이용하여 계속적인 힘을 더한다.
-ForceMode.Acceleration - 계속적인 가속을 더하고 오브젝트의 질량은 무시한다.
-ForceMode.Impulse - 오브젝트의 질량을 이용하여 충격력 인스턴트를 더한다.
-ForceMode.VelocityChange - 속도 인스턴트를 더하며, 오브젝트의 질량은 무시한다.

'velocity'는 Rigidbody의 속도를 나타냅니다. '오브젝트의 질량과 상관없이' 일정 속도를 줍니다.
이동에 관한 함수는 우선 이정도만 정리하자

다음 코드는 OnCollisionEnter함수이다.
우선 물체의 Collider에 다른 오브젝트가 감지되었을 때 불려지는 함수로 해당 스크립트에서는 현재 활성화 되어있는 씬을 재시작한다.
LoadScene함수에 관해서 잘 정리해놓은 블로그가 있어서 링크를 달아놓아야겠다.
https://ansohxxn.github.io/unitydocs/scenemanager/ 

다음은 주석처리를 한 코드를 살펴보자
해당 오브젝트의 MeshRenderer 컴포넌트를 가져와 material의 color를 랜덤값으로 변경해주었다.
따라서 해당 오브젝트는 점프를 할 때 마다 rgb값이 랜덤값으로 변경이 된다.

![image](https://github.com/Been98/Been98.github.io/assets/85021523/aae5a27a-8280-4ed7-813b-b1c1c5748c44){: .align-center}
'Wall.cs'
{: .notice--primary} 
이 코드는 간단하게 Player오브젝트가 가지고 있는 Player.cs를 가져와 벽이 삭제될 때 점수 1점을 추가한다. 여기서 벽은 위에서 정리한 Translate를 이용해 움직이고 있음을 알 수 있다. 
벽의 x포지션 값이 -10을 넘어가면 벽을 Destroy한다. 
여기서 궁금한 점은 Destroy를 하고 난 후에 코드들은 실행이 될까? 이다.



본 후기는 유데미-스나이퍼팩토리 10주 완성 프로젝트캠프 학습 일지 후기로 작성 되었습니다.
#프로젝트캠프 #프로젝트캠프후기 #유데미 #udemy #스나이퍼팩토리 #웅진씽크빅 #인사이드아웃 #IT개발캠프 #개발자부트캠프 #unity #유니티 #게임개발 #메타버스 