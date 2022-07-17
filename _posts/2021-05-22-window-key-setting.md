---
layout: post #Do not change.
category: [record] #One, more categories or no at all.
title: "[Windows] Capslock키와 Ctrl키 바꾸기" 
author: 또치 
date:   2021-05-22 21:09:43 +0900
<!-- nextPart: _posts/2021-01-30-example.md #Next part. -->
<!-- prevPart: _posts/2021-01-30-example.md #Previous part. -->
<!-- og_image: assets/post-imgs/img/ai.jpeg #Open Graph preview image. -->
<!-- og_description: "Example description." #Open Graph description. -->
<!-- fb_app_id: example -->
---

nvim을 사용하다보면 Ctrl키를 사용할 때가 많아 Ctrl과  Capslock을 바꿔서 사용해왔다. 맥북같은 경우에는 키보드 환경설정에서 보조키를 쉽게 변경할 수 있다. 하지만 일할때에는 윈도우를 사용하다보니 너무 불편했다. 그래서 결국 레지스트리를 통해 바꿔주었다.👍

## CapsLock, Ctrl 바꾸기 

1.&nbsp;레지스트리 편집기 실행 ( window+r &nbsp; -> &nbsp; regedit 입력 )

2.&nbsp;HKEY LOCAL MACHINE/SYSTEM/CurrentControlSet/Control/Keyboard Layout 으로 이동

3.&nbsp;새로 만들기 &nbsp; -> &nbsp; 이진값(binary value) 생성

4.&nbsp;이진값 입력
> 00 00 00 00 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; => &nbsp; &nbsp;  Header   
00 00 00 00 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; => &nbsp; &nbsp;  Version   
00 03 00 00	&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; => &nbsp; &nbsp;  수정할 키 개수(+1)  
1d 00 3a 00 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; => &nbsp; &nbsp;  1d(CapsLock) 3a(Left Ctrl)  
3a 00 1d 00 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; => &nbsp; &nbsp;  CapsLock 안 쓸줄 알고 안했다가 뒤늦게 추가해줬다  
00 00 00 00 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;=> &nbsp; &nbsp; 종료

5.&nbsp; 재부팅 


<br/>
<br/>
결과 페이지👏👏👏
<p align='center'>
 <img src="/assets/img/post-imgs/keyboard_setting.PNG" height='500px' align='center'/>
</p>




