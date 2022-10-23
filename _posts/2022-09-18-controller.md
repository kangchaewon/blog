---
layout: post
title: controller
categories: java springboot
tags: [java][springboot] 
---

controller의 역할
------------------

 사용자의 요청이 처음 진입하는 지점이며 정보를 데이터로 받고, 원하는 곳으로 주는 역할을 한다.

controller를 쓰는 방법
----------------------

1. 기본 

```java  
@RequestMapping("/api");

@GetMapping("/test")
public String testMethod(){
    return "안녕 ~~아";
}
```
+ 이것을 웹주소로 localhost:8080/api/test를 입력한다.

<img src="https://kangchaewon.github.io/blog/assets/images/post/post_controller_1.jpg" width="490px" height="294.5px" title="1번 이미지"/>

2. 숫자

```java  
@RequsetMapping("/api");

@GetMapping("/test2")
public int test2Method(@RequestParam int number) {
        return number+10;
}
```
+ 이것을 웹주소로 localhost:8080/api/test2?number=1을 입력한다.

<img src="https://kangchaewon.github.io/blog/assets/images/post/post_controller_2.jpg" width="980px" height="589px" title="2번 이미지"/>  

3. 문자

```java  
@RequsetMapping("/api");
@Slf4j

@GetMapping("/test2")
@GetMapping("/test3/{name}")
    public String test3(@PathVariable("name") String name){
        log.error("test3 Controller 실행");
        return "안녕하세요. 저는 " + name + "입니다.";
    }
```

+ 이것을 웹주소로 localhost:8080/api/test3/강채원을 입력한다.

<img src="https://kangchaewon.github.io/blog/assets/images/post/post_controller_3.jpg" width="980px" height="589px" title="3번 이미지"/>