---
title: K-Community 2
date: 2024-01-29 19:00:00 +0900
categories: ['2024', 'K-Community']
pin: true
---

#### 1편을 보지 않았다면, [이전 게시글](https://hs-p.github.io/posts/Kcommunity)를 참고하길 바란다.

# 결과

---

우리는 밤을 세워가며 열심히 터틀봇을 두들기고, 애원하고, 기도했다.
결과적으로는 운이 좋았던 어느 날에 성공하게 되었다.

OpenCR Firmware을 업로드하고, Dynamixel Test를 진행하자 '위이잉-' 소리를 내며 바퀴를 움직였고,

``` console
$ ros2 launch turtlebot3_bringup robot.launch.py
```
를 실행하자  Run!이라는 기분 좋은 명령과 함께, 새로운 터미널을 열어 ssh로 연결한 후.  

```console
$ ros2 run turtlebot3_teleop teleop_keyboard
```

를 실행하고 키를 누르자 **정상적으로 움직이기 시작**했다.  
이 때가 이 로봇의 전성기였다.  

그렇게 영상을 촬영하고, 아래에 내려놓고 키 입력을 시작하자 조금 앞으로 가더니 이내 멈춰버리고 말았다.  

싸한 기분, 선이 끊겼나, 배터리가 다 되었나 확인해 보았지만 더 이상 움직이지 않았다.  
그 때를 기점으로 더 이상 Dynamixel은 Scan되지 않고 멀리 떠나가버렸다.  
*(필자는 아직도 그 때가 아른거린다.)* 

SW 1팀에서 시뮬레이션 세팅을 전부 완료했었던 우리 팀은 가제보와 알비즈(Gazebo and Rviz)가 그냥 그림의 떡이 되어버렸다.  
단순히 시뮬레이션 Tool, 연결되어 같이 움직이며 SLAM을 할 수 있을거라 잠시나마 기대했던 자신이 바보같았다.  

![Image](/posts/kc52.png)

*Gazebo Simulation을 실행한 결과.*


# 발표

---

우리는 이 결과를 이제 잘 포장해서 발표를 해야 했다.  
초기 목표에서는 어긋나 있을지 몰라도, 우리는 무려 **구동**을 했다.
라즈베리파이의 '라'도 모르던 사람들끼리 모여 아래와 같은 활동을 한 것이다.
```
1. Ubuntu Desktop 22.04 LTS 가상 환경 조성
2. Ubuntu, Windows Dual boot 환경 조성
3. RaspberryPI 사전 Rasbian OS에서 Ubuntu Server OS로 SD Card 변환 후 설치
4. Opencr 1.0 Firmware Setup
5. Dynamixel Wizard 사용 Dynamixel Scan
6. Linux Ubuntu 환경에서의 Ros Package install, build
7. 스무 여가지의 크고 작은 오류 해결
```

물론, 터틀봇을 움직여본 사람들이라면 모두 겪은 간단한 일이긴 하다.

![Image](/posts/kc61.png)

우리는 이걸 잘 포장해서 발표를 하기 위해 모든 빌드업 과정을 거쳤다.  
우리는 감자라는 사실을 사람들에게 인식시키고, 이후 이런 성장을 이뤄낸 주인공 같은 이야기 말이다.  

결과적으론 우리는 잘 발표를 마무리했다.  
(시간이 적어서 조금 급하게 하고, 설명을 자세히 하지 못한 점이 아쉬웠다.)

![Image](/posts/kc62.png)

활동 결과로 결국 바퀴가 움직이는 걸 보여줬다.  
마치 화룡점정에 찍은 것 같지만, 실제로는 그냥 연결해서 구동해본 것이다.  
만약 Ubuntu 22.04 Ros2 Humble 환경에서 Turtlebot Setup하는 과정이 얼마나 어려운 과정인지 설명할 수 있었다면,  
그 시간이 주어졌다면 **열변**을 토했을텐데 말이다.  

그래도 우리의 실력이 늘었다는 점에서는 아주 흡족스러웠다.  
Ubuntu 환경, Ros 활용 능력에 대한 이해도가 미친듯이 높아졌다.  
물론 실제 개발자들에 비하면 세발의 피겠지만, 실력이 0.1에서 10으로 증가한거면 **100배나 증가**한 것이니까.  

이 베이스를 가지고 이제 [Ros2 교육](https://hs-p.github.io/posts/ros1)을 받으러 이동했다.
**Ros 교육에 대한 포스트**는 위 링크를 따라 이동하면 엿들을 수 있다.