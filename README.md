 <div align="center"><img src="https://user-images.githubusercontent.com/55028104/101986756-3cc15000-3cd3-11eb-9458-e2183839231b.PNG" alt="logo"  width="600" />    
 </div>
 <br>
 <div align="center">

__😎 Team__  
🔥 __BLOCKBUS_TOP__ 🔥  
<br/>

__🥰 Member__  
[사영훈](https://github.com/tkdudgns95) | [유혜상](https://github.com/Yuhye) | [이창해](https://github.com/vip7gain) | [전민수](https://github.com/GodofPig) | [차민재](https://github.com/charmingjae)  

</div>

<br/>

* * *
<br/>


<div align="center">

## __음주운전 방지를 위한 차량부착형 MQ-3 알코올 감지 키트__<br/>
*Vehicle-attached MQ-3 alcohol detection kit for preventing drunk driving*
</div><br/>

* * *
<br/>

## 🚩 __Contents__

1. __📖 Abstract__
2. __📦 프로젝트 소개__
3. __🌊 Flow-chart__
4. __⚙️ 사용 품목__
5. __🍒 라즈베리파이 구성도__
6. __🥳 문제점과 해결과정__
7. __👩🏻‍💻 시연__
8. __🎉 EFFECT__
9. __Q&A__

<br/>
<br/>

## __📖 Abstract__
<p align="center"><img src="https://user-images.githubusercontent.com/55028104/101987654-e3f4b600-3cd8-11eb-8a66-434f1d07e1d4.jpeg" alt="drive" width="400"/></p>
<br/>
 
사람들은 음주 후의 운전의 위험함과 심각성을 충분히 인지하고 있지만, 음주운전으로 인한 사고 비율은 [__여전히 높은 추세 이다.__](https://search.naver.com/search.naver?where=news&sm=tab_jum&query=%EC%9D%8C%EC%A3%BC%EC%9A%B4%EC%A0%84)  
따라서 라즈베리파이를 이용하여 가격, 활용 면에서 실용적이고 운전자의 음주운전을 예방하고자 본 프로젝트를 진행하게 되었다.
<br/>

-----------------------------------------------------------------      
<br>

## __📦 프로젝트 소개__
 
<p align="center"><img src="https://user-images.githubusercontent.com/55028104/101986434-2dd99e00-3cd1-11eb-9627-da640e38ac69.jpg" alt="car" width="400"/></p>  
<br/>

본 프로젝트의 주제는 __차량 부착형 알코올 감지 키트__ 이다. 운전자의 음주 여부를 판독하기 위해 운전자의 __날숨을 감지할 수 있는__ 차량의 대시보드(Dashboard), 핸들 등의 위치에 부착된다.

이 키트는 __MQ-3 센서__ 를 이용해 알코올을 감지한다. 만약, 이 센서에 알코올이 감지 되면 붉은 LED와 부저를 통해 운전자에게 __음주 상태라는 상황을 인식__ 시킨다.  
그 후 선언된 파이썬 함수를 통하여 텔레그램으로 메시지를 보내 가족이나 친구 등의 지인들에게 __운전자의 상태를 전송__ 한다.

<br/>

-------------------------------------------------------------------
<br/>

## __🌊 Flow-chart__
<p align="center"><img src="https://user-images.githubusercontent.com/55028104/101988164-4fd81e00-3cdb-11eb-8034-b2187fb11fb7.PNG" alt="schematization"/></p>

<br>

1. 먼저 운전자의 날숨을 MQ-3 센서에서 감지 해 __기준 값(Reference) 보다 낮으면__ 루프를 돌면서 지속적으로 감지한다.  
2. 만약 기존 값(Reference) 보다 __감지 값(Levels)가 높다면__ LED와 부저(Buzzer)가 작동한다.  
3. 그 후에 텔레그램으로 운전자의 상태가 전송되며 전송이 된 후 LED와 부저는 작동을 멈추고 다시 처음으로 돌아가 날숨을 감지하는 과정을 수행한다.

<br/>

-------------------------------------------------------------------

<br/>
<br/>

## __⚙️ 사용 품목__
<br>
 <img src="https://user-images.githubusercontent.com/55028104/102213357-f90c5780-3f19-11eb-876a-d7ed229707db.jpg" alt="sensor"/></p>

 <br>
 
* **MQ-3 센서**
  * 가스센서 모듈로 센서 내부 히팅 코일 가열을 통해 알코올을 감지한다.
  * 공기 중의 알코올 분자로 인해 전자가 발생되면 저항 값이 낮아져 전류량이 증가한다.

* **LED**
  * 붉은 색의 LED로, 사용자에게 __시각적으로 위험을 전달__ 하기 위해 사용.  
* **부저**
  * 알코올 감지 시 LED와 같이 위험을 전달하는 요소로, 청각적 신호를 주는 센서.
* **브레드보드**
  * 통로 역할을 해주는 자재로 원활한 전기 흐름을 구성하기 위해 사용.
  * 납땜을 하지 않아도 되기 때문에 라즈베리파이 회로 구현에서 쉽게 사용된다.
  * 본 프로젝트에서는 라즈베리파이에 상단의 센서들을 연결하기 위해 사용된다.

<br>

-------------------------------------------------------------------

<br>
<br> 

## __🍒 라즈베리파이 구성도__

<br>
 <p align="center"><img src="https://github.com/charmingjae/raspberry/blob/master/img/configuration%20V2.png" alt="configuration"/></p>
 <br>
 
 **MQ-3 센서, LED, 부저, 저항** 을 연결한 **브레드보드** 를 **라즈베리파이** 에 연결한 구성도이다.
 
  <br>

<br>
<br> 

-------------------------------------------------------------------

<br>
<br>  

## __🥳 문제점과 해결과정__

<br>
<br>
<br>


1. **하드웨어적인 결함**
  * 테스트 결과 정상적인 코드 실행에도 하드웨어적인 결함으로 사운드가 들리지 않는 문제가 있었다.  
  하지만, __새로운 MQ-3 센서의 탑재__ , 브레드보드를 거쳐서 연결하던 연결방식을 __직접 연결 방식으로 변경__ 해 문제를 해결하였다.
<br>  
<br/>

2. **보급의 문제**
  * 서비스를 이용하기 위해서 해당 기기를 보급하여 차량에 설치해야 한다는 점과 차량 내 인터넷이 활성화 되어야 하는 문제가 있다.  
  먼저, 기기 보급에 대한 문제는 상용화 시 저가의 하드웨어로 쉽게 보급할 수 있다는 점을 활용해 해결 할 수 있고,  
  차량 내 인터넷 문제는 __지그비(Zigbee) 통신__ , 라즈베리파이에 __와이파이 모듈__ 을 연결해 해결할 수 있다.
<br>
<br>
 
3. **제도,법률,도덕적인 문제**
  * 서비스를 위한기기를 운전자가 반드시 설치, 이용해야 한다는 제도 그리고 법률적인 조항이 없어, 개인의 도덕적인 판단으로 기기 설치와 서비스 이용을 맡겨야 한다는 점에서 어려움을 가질 수 있다.
<br>
<br>
 
-------------------------------------------------------------------

<br>
<br> 

## __👩🏻‍💻 시연__

<br>
 <img src="" alt=""/>
 <div align="center">

 __👨🏻‍💻 데모 영상 - 초기 흐름도 구현👨🏻‍💻__

 </div>

 ![demo](https://user-images.githubusercontent.com/54883521/102215101-98324e80-3f1c-11eb-92a0-441e723588b1.gif)

<br/><br/>

<div align="center">

__👨🏻‍💻 텔레그램(Telegram) 연동 👨🏻‍💻__

![demo_telegram](https://user-images.githubusercontent.com/54883521/102220329-00386300-3f24-11eb-9c7d-c18722b48041.gif)

</div>

<br/><br/><br/>
<div align="center">

__👨🏻‍💻 최종 시연 영상 👨🏻‍💻__

[__☘️ 보러가기☘️__](https://www.youtube.com/watch?v=f0wG7AQW8mU)

</div>



 <br>

-------------------------------------------------------------------
<br>
<br>

## __🎉 EFFECT__

<br>
 <img src="" alt=""/>
 
* LED와 부저를 사용하여 운전자의 음주여부를 시/청각화 가능.


* 텔레그램 메시지 전송을 통해 주변인들의 적극적인 제지 기대.
 
 <br/>

-------------------------------------------------------------------

<br>
<br> 
 
<h1 align="center"> Q & A </h1>

 <br>

