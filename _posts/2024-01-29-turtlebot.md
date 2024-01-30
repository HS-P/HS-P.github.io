---
title: Turtlebot3 WafflePI (Ubuntu 22.04)
date: 2024-01-29 20:50:00 +0900
categories: ['2024', 'Turtlebot3']
pin: true
---

# Overview

---

Turtlebot3는 [K-Community 학습 동아리](https://hs-p.github.io/posts/Kcommunity)에서 RaspberryPI, ROS 공부를 위해 다뤘다.  
현재는 랩실에 다시 반납한 상태로, 후에 다시 사용이 가능하다면 글을 올리겠다.  
이 게시글에서 다룰 내용은 터틀봇3 WafflePI, ROS2 Ubuntu 22.04 Humble 환경에서 작업하는 사람들을 위해 작성되었다.  
*(본 필자는 현재 Raspberry PI 5, Rasbian OS에서 Docker를 이용하여 Ubuntu 22.04, ROS2를 실행하고 있다.)*

# PRE-SETUP

--- 

본 기준은 **Turtlebot3 Waffle PI** 를 기준으로 작성되었다.
혹여 **Burger**라던가, **Waffle**이라면 알아서 잘 걸러서 이해하길 바란다.

## TURTLEBOT

터틀봇은 [Robotis](hsttps://emanual.robotis.com/docs/en/platform/turtlebot3/overview/)에서 만든 라즈베리파이와 OPENCR, LAIDAR 센서 등을 잘 조합해서 구매자가 쉽게 사용할 수 있도록 만든 로봇이다.  
사전 동봉된 물품들만 잘 있다면, 문제 없이 Setup하는 과정을 잘 거칠 수 있다.  
*(필자처럼 멍청하지 않다면 말이다.)*

WafflePI는 기본적으로 가격대가 조금 나간다.
![Image](/posts/tu1.png)

**조금**이 아닌가? 라는 생각이 들 수도 있지만, 각 부품들의 가격대가 원래 비싸기 때문에 어쩔 수 없는 것 같기도 하다.  
일반 학생들이 사비로 사기엔 엄두가 나지 않는 큰 금액이다.  

## Installation

설치는 위 로보티즈 사이트에서 상당히 자세하게 설명되어 있다.    
[[로보티즈 퀵스타트 가이드]](https://emanual.robotis.com/docs/en/platform/turtlebot3/quick-start/)  

위 가이드를 순서대로 따라가다 보면, 발생할 만한 문제에 대해서 다뤄보겠다.  
일단, 대부분 우분투에 관한 문제가 발생할 것인데, 우분투에 관한 문제는 [우분투 게시글](https://hs-p.github.io/posts/second/)에서 확인하면 된다.  

ROS에 관련한 문제가 발생한 내용에 대해서만 정리해 두겠다. 

>1. Bashrc error (cannot found, etc)
> ~/.bashrc가 갖는 역할에 대해 잘 모른다면 위 우분투 게시글을 반드시 들어가서 참고하도록 한다.
> 만약 bashrc에 두 개 이상의 Workspace가 할당되어 있으면, ROS가 정상 실행이 되지 않을 수 있다.
> 즉, setup.bash가 두 개 이상인지 확인하라. (여러 튜토리얼을 진행하다 보면 Workspace 혼선이 올 가능성이 있다.)

>2. Colcon build error
> 사실 이것 때문에 작성을 했다고 해도 과언이 아니다.
> RaspberryPI 3B+ 모델을 착용하고 있었는데, Ram 용량이 1GB밖에 되지 않아 문제가 발생했다.
> 구글링시 램 할당량을 2GB 이상으로 늘리라는데, 모델의 RAM 용량이 1GB밖에 되지 않아 불가능하다.

Colcon Build의 경우, Github 내에서 각각 주요 Package들을 찾아서 따로따로 build 해 주어야 한다.  
*(그렇지 않으면 멈춰버리고 blocked for more than 120 seconds 에러가 발생해 버린다.)*

# During Run

---

OPENCR