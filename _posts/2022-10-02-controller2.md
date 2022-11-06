---
layout: post
title: controller 문제
categories: java springboot problem
tags: [java][springboot]
---

Controller 문제
=====================

1. member API 개발

```java
@GetMapping("/member")
    public String MemberMethod (){
        return "회원리스트입니다.";
    }
```
+ response 타입이 String이고, 또한 response가 회원리스트이다.

2. member 상세 API 개발

```java
 @GetMapping("/member/{userid}")
    public String MemberMethod2 (@PathVariable ("userid") String userid){
        log.error("member2 실행");
        return userid + "의정보입니다.";
    }
```
+ response 타입이 String이고, response가 {userid}의 정보이고, userid의 타입은 int이다.
+ parameter은 PathVariable을 사용했다. 

3. Calculate API 개발

```java
 @GetMapping("/calculate?number1={number1}&number2={number2}")
    public String CalculateMethod (@PathVariable("number1")int number1,@PathVariable("number2")int number2){
        log.error("calculatemethod 실행");
        int sum=number1+number2;
        return "sum";
    }
```
+ response 타입은 String이고, response가 number1+number2의 합이며 number1,number2의 타입은 int이다.
+ parameter은 QueryParam을 사용했다. 

4. Calculate API 개발2

```java
@GetMapping("{type}calculate?number1={number1}&number2={number2}")
    public String CalculateMethod2 (@RequestParam String type, @PathVariable("number1")int number1, @PathVariable("number2")int number2){
        log.error("calculate method 실행");
        int sum=0;
        if(type=="plus"){
            sum=number1+number2;
        } else if (type=="minus") {
            sum=number1-number2;
        } else if (type=="multiple") {
            sum=number1*number2;
        } else if (type=="division") {
            sum=number1/number2;
        }
        return number1+ "와 " + number2 +"의 "+ type + "는(은) "+ sum + "입니다.";
    }
```
+ response 타입은 String 이며, response number1와 number2의 {type}은 ㅌㅌㅌ이고, parameter은 PathVariable을 사용하였다.
+ 또한 type의 타입은 String이며, number1,number2의 타입은 int이다.