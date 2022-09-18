---
layout: post
title: controller
categories: java
tags: [java]
---

controller의 역할
------------------
 사용자의 요청이 진입하는 지점이며 요청에 따라 어떠 처리를 할지 결정을 Service에 넘겨줍니다. 그후, Service에서 실질적으로 처리한 내용을 View에게 넘겨줍니다.

controller를 쓰는 방법
----------------------

1. 
```java
@GetMapping("/test")
public String testMethod(){
    return "안녕 ~~아";
}
```
+ 이것을 localhost:8080/test를 입력한다.
<img src="./assets/images/post/post_controller_1.jpg" width="100px" height="50px" title="1번 이미지"/>