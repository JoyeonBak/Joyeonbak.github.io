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


#### 제어문
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


#### 변수 n에 저장된 10진수를 2진수로 변환 출력
```JAVA
public class Test{
    public static void main(String[] args){
        int a[] = new int[8];
        int i = 0;
        int n = 10;
        while(n > 0){
            //처음에 a[0]에 값을 넣고나서 i++ 역할
            a[i++]=(n % 2);
            n /= 2;
        }
        for(i=7; i>=0; i--)
            System.out.print(a[i]);
    }
}
```


```JAVA
public class Test{
    public static void main(String[] args){
        int i = 0, c = 0;
        while(i < 10){
            i++;
            c *= i;
        }
        System.out.println(c);
    }
}
//출력 : 0
```


```JAVA
public class Test{
    public static void main(String[] args){
        int a = 0, sum = 0;
        while(a < 10){
            a++;
            if(a % 2 == 1){
                continue;
                sum += a;
            }
            System.out.println(sum);
        }
    }
}
//출력 : 30
```


#### ary[][]
* ary[i][j] : i는 크게 배열 개수, j는 그 안의 배열 요소 수
    <span style="color:#808080">*ary[][]={{1,2,3},{5}} 일 때, ary[0][0]=1, ary[0][2]=3 그리고 ary[0].length = 3*</span>
```JAVA
public class Test{
    public static void main(String[] args){
        int ary[][] = new int [3][5]
        int n = 1;
        for(int i = 0; i < 3; i++){
            for(int j = 0; j < 5; j++){
                ary[i][j] = j * 3 + i + 1;
                System.out.print(ary[i][j] + " ");
            }       
        }
        System.out.println();
    }
} 
```


```JAVA
public class Test{
    public static void main(String[] args){
        int j, i;
        for(j=0,i=0; i<=5;i++){
            j += i;
            System.out.print(i);
            if(i==5){
                System.out.print("=");
                System.out.print(j);
            }
            else
                System.out.print("+");
        }
    }
}
//출력 : 0+1+2+3+4+5=15
```


#### a, b 에 각각 8 과 3을 입력했을 때 결과는?
```JAVA
public class Test{
    public static void main(String[] args){
        Scanner scan = new Scanner(System.in);
        int a = scan.nextIn();
        int b = scan.nextIn();
        char c = 'G';

        if(a > 10 && b < 10){
            if(a - b < 5 || a > 15)
                c = 'X';
        }
        else if(a > 5 && b < 5){
            if(a - b < 3 || b > 0)
                c = 'Y';
        }
        else
            c = 'Z';

        System.out.printf("%c", c);
        scan.close();
    }
}
//출력 : Y
```


```JAVA
public class Test{
    public static void main(String[] args){
        String str = "Programming";
        int n = str.length();
        char[] st = new char[n];
        n--;
        for(int k=n; k>=0; k--){
            st[n-k] = str.charAt(k);
        }
        for(char k : st){
            System.out.printf("%c", k);
        }
    }
}
//출력 : gnimmargorP
```


### Java 클래스
* public static void main(String[] args)  
: 모든 Java 프로그램은 실행용으로 만든 클래스 안에 반드시 main() 메소드가 있어야 실행이 시작된다.


```JAVA
class ClassA{
    int a = 10;
    int funcAdd(int x, int y){
        return x + y + a;
    }
}
public class Test{
    public static void main(String[] args){
        int x = 3, y = 6, r;
        ClassA cal = new ClassA();
        r = cal.funcAdd(x,y);
        System.out.print(r);
    }
}
//출력 : 19
```

* 일반적으로 어떤 클래스의 메소드를 호출하려면 메소드가 포함된 클래스의 객체 변수를 선언한 후 호출해야 한다.  
  아래(Test.check(1))와 같이 호출하는 경우에는 호출되는 메소드가 static으로 선언되어야 한다.


```JAVA
public class Test{
    public static void main(String[] args){
        System.out.print(Test.check(1));
    }
    static String check(int num){
        return (num >= 0) ? "positive":"negative";
    }
}
```


* 아래 recursive 메소드의 쓰임과 같이 반복적으로 사용될 때, 반환 값만 가져오지 않고  
메소드 안 실행문들은 모두 실행을 하고 반환값을 대입해야 함.


```JAVA
import java.utill.Scanner;

public class Test{
    public static void main(String[] args){
        int i;
        Scanner s = new Scanner(System.in);
        System.out.print("숫자를 입력하시오: ");
        i = s.nextInt();
        recursive(i);
        s.close();
    }
    static int recursive(int n){
        int i;
        if(n < 1)
            return 2;
        else {
            i = (2 * recursive(n-1))+1;
            System.out.println(i);
            return i;
        }
    }
}
/*
출력 :
5
11
23
47
95
*/ 
```


```JAVA
public class Test{
    static int[] arr(){
        int a[] = new int[4];
        int b = a.length;
        for(int i=0; i<b; i++){
            a[i] = i;
            return a; //a=[0,1,2,3]
        }
    }
    public static void main(String[] args){
        int a[] = arr();
        for(int i=0; i<a.length; i++)
            System.out.print(a[i]+" ");
    }
}
//출력 : 0 1 2 3
```


#### 생성자(지정 기능)
어떤 클래스(의 메소드)를 사용하기 위해선 꼭 매개변수가 지정되어야 한다고 할 때, 생성자를 만들어야 한다.  
*예를 들어, 어떤 메소드를 쓸 때는 매개변수가 필요한데 그 클래스의 메소드를 호출할 때, 매개변수 넣지 않고 호출 할 수도 있기 때문에!*


```JAVA
class A{
    int a;
    public A(int a){this.a = a;}
    void display(){System.out.println("a="+a);}
}
class B extends A{
    public B(int a){
        /*
            아래 의미는 클래스 변수 = new 클래스(a)로 객체 변수 선언한 것.
            여기서 클래스는 상속받은 클래스니까 A
        */
        super(a); 
        //객체 변수 선언 후, 그 클래스의 메소드를 호출
        super.display();
    }
}
public class Test{
    public static void main(String[] args){
        B obj = new B(10);
    }
}
```

### Java 활용





<!-- 
```JAVA
public class Test{
    public static void main(String[] args){
        
    }
}
```
-->



출처 :  
<https://noritersand.github.io/java/java-%EC%97%B0%EC%82%B0%EC%9E%90-operator/>
<https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=james_parku&logNo=110166236377>