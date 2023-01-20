---
layout: post
title: "[Java] 기초 문제"
subtitle: 
categories: Java
tags: [Java]
--- 
## 정보처리기사 실기 기반  

제어문자    | 기능
\n        | 다음 줄 처음으로 이동
\t        | 커서 일정 간격 띄움
\0        | null 문자 출력



서식 문자열 | 의미
%d       | 정수형 10진수 입/출력
%o       | 정수형 8진수 입/출력
%x       | 정수형 16진수 입/출력
%c       | 문자형 입/출력
%s       | 문자열 입/출력
%f       | (소수점 포함)실수형 입/출력, 출력 시 기본 소수점 6자리까지


```JAVA
import java.util.Scanner;

public class Test{
    public static void main(String[] args){
        //System.in : 표준입력장치로 입력된 값(키보드)
        Scanner scan = new Scanner(System.in);
        int a = scan.nextInt();
        System.out.printf("a * 3 = %d\n", a * 3);
        System.out.println("a / 2 = " + (a / 2));
        System.out.print("a - 1 =" + (a - 1));
        scan.close(); //닫아줘야 메모리를 다시 다른 프로그램이 사용할 수 있다.
    }
}
```

### 연산자 우선순위
<img src="/assets/images/banners/java-operator-1.png" >


```JAVA
public class Test{
    public static void main(String[] args){
        int w = 3, x = 4, y = 3, z = 5;
        if((w == 2 | w == y) & !(y > z) & (1 == x ^ y != z)){
            w = x + y;
            if(7 == x ^ y != w)
                System.out.println(w);
            else
                System.out.println(x);
        }
        else{
            w = y + z;
            if(7 == y ^ z != w)
                System.out.println(w);
            else
                System.out.println(z);
        }
    }
}

//출력 : 7
```
<img src="/assets/images/java/8.jpeg" >  


<img src="/assets/images/java/9.jpeg" >  


<img src="/assets/images/java/10.jpeg" >  


<img src="/assets/images/java/11.jpeg" >  


<img src="/assets/images/java/12.jpeg" >  


<img src="/assets/images/java/13.jpeg" >  


```JAVA
//거짓은 0, 참은 1
public class Test{
    public static void main(String[] args){
        int a = 5, b = 9, c;
        c = b % 5 < 5 ? 1 : 0; //c = 1
        /*
            쉬프트연산자
            c << 3 : c를 왼쪽으로 3번 이동(1*2*2*2)
            비트연산자 비교
            1 | 8 : 둘 다 비트형으로 변형 후 비교. 다르면 1, 1로 같으면 1, 0으로 같으면 0
        */
        c = c | c << 3;
        c = a < 5 || c >= 10 ? c - a : c + a;

        System.out.printf("%d", c);    
    }
}
//출력 : 14
```


```JAVA
public class Test{
    public static void main(String[] args){
       string str = "agile";
       int x[] = {1, 2, 3, 4, 5};
       char y[] = new char[5];
       int i = 0;

       while(i < str.length()){
        //y[i]에 str의 i번째에 있는 문자를 저장
        y[i]=str.charAt(i);
        i++;
        }
        /*
            향상된 for문
            x배열의 각 요소 값을 차례로 받으면서 요소 수 만큼 반복 수행!
        */
       for(int p : x){
        i--;
        System.out.print(y[i]);    
        System.out.print(p + " ");    
        }
   }
}
//출력 : e1 l2 i3
```


* break : 반복문 또는 switch문 안에서 break가 나오면 블록을 벗어남
* continue : 반복문에서 continue가 나오면 그 이후의 문장들은 실행하지 않고  
             다시 반복문의 처음으로 돌아가 다음 반복문 진행  


출처 :  
<https://noritersand.github.io/java/java-%EC%97%B0%EC%82%B0%EC%9E%90-operator/>
<https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=james_parku&logNo=110166236377>