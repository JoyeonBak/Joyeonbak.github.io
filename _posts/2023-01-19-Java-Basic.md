---
layout: post
title: "[Java]기초 문제"
subtitle: 
categories: Java
tags: [ava]
--- 
## 정보처리기사 실기 기반

```JAVA
import java.util.Scanner;

public class Test{
    public static void main(String[] args){
        //System.in : 표준입력장치로 입력된 값(키보드)
        Scanner scan = new Scanner(System.in);
        int a = scan.nextInt();
        System.out.printlf("a * 3 = %d\n", a * 3);
        System.out.println("a / 2 = " + (a / 2));
        System.out.print("a - 1 =" + (a - 1));
        scan.close(); //닫아줘야 메모리를 다시 다른 프로그램이 사용할 수 있다.
    }
}
```

제어문자 | 기능
\n     | 다음 줄 처음으로 이동
\t     | 커서 일정 간격 띄움
\0     | null 문자 출력

