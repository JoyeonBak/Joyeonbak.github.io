---
layout: post
title: "[Java] BufferedReader, BufferedWriter"
subtitle: 
categories: Java
tags: [Input, Output, I/O, BufferedReader, BufferedWriter, Java]
--- 
입력 방식을 통하여 시간복잡도를 줄이는 방법


## Scanner vs. BufferedReader
* Scanner를 사용하는 방법


```JAVA
Scanner sc = new Scanner(System.in);
int n = Integer.parseInt(sc.nextLine());
```

* BufferedReader를 사용하는 방법


```JAVA
BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
int n = Integer.parseInt(br.readLine());
```


여기서 스캐너의 경우 내부적으로 다음 입력을 위한 정규식을 사용하므로 느리지만 버퍼의 경우 키보드로 입력을 받게되면 해당 문자들을 버퍼에 저장했다가 버퍼가 가득차거나 개행문자가 들어오면 이를 한번에 전송하는 방식을 사용한다.  
이와 같은 맥락으로 출력의 경우도 똑같다. BufferedWriter를 사용해 버퍼를 이용한다. 이때 꼭 close를 해 주어야한다. 


```JAVA
BufferedWriter bw = new BufferedWriter(new OutputStreamReader(System.out));
String str = "A";
bw.write(str);
bw.flush();
bw.close();   //닫기
```


## BufferedReader
Input Class

* readLine( ) : 입력값으로 들어온 데이터를 한 줄로 읽고 String으로 바꾸는 메소드. 무조건 한 줄만 읽음
* Integer.parseInt( ) : int 타입으로 변경
* StringTokenizer 또는 split( ) : "1", "2", ... "5" 로 따로 입력을 읽고, 배열에 삽입
* close( ) : 닫기
* 반드시 IOException 예외 처리!


```JAVA
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.StringTokenizer;

public class Main {

	public static void main(String[] args) throws IOException {
		//BufferedReader를 사용하기 위해서는 throws IOException을 해 주어야 함.
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in)); // 선언

        //readLine으로 받은 입력 데이터는 String 이므로
		int N = Integer.parseInt(br.readLine()); 
		//배열로 넣기
        int[] arr = new int[N];

		StringTokenizer st = new StringTokenizer(br.readLine());
		for (int i = 0; i < N; i++) {
			arr[i] = Integer.parseInt(st.nextToken());
		}

		br.close();
	}
}

```


## BufferedWriter
* write( ) : 출력할 내용 담기
* flush( ) : 버퍼를 비워내면서 출력. 반드시 flush( )를 사용해야 출력이 됨.
* 반드시 IOException 예외 처리!


```JAVA
import java.io.BufferedWriter;
import java.io.IOException;
import java.io.OutputStreamWriter;

public class Main {

	public static void main(String[] args) throws IOException {
	    //BufferedWriter를 사용하기 위해서는 throws IOException을 해 주어야 함.
        
        //선언  
		BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
		bw.write("Hello World");
        //write로 담은 내용 출력 후, 버퍼를 비움.
		bw.flush(); 
		bw.close(); 
	}
}
```


출처 :  
<https://blog.naver.com/wwa1102/222982726971>  
<https://steady-coding.tistory.com/184>  