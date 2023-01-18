---
layout: post
title: "[Algorithm_Java] 구간 합 구하기"
subtitle: 
categories: Algorithm
tags: [Algorithm, 알고리즘]
--- 
### 구간 합 구하기
Q. 수 N개가 주어졌을 때 i번째 수에서 j번째 수까지의 합을 구하는 프로그램을 작성하시오.

#### 입력
1번째 줄에 수의 개수 N (1 ≤ N ≤ 100,000), 합을 구해야 하는 횟수 M (1 ≤ M ≤ 100,000),  
2번째 줄에 N개의 수가 주어진다. 각 수는 1,000보다 작거나 같은 자연수다.  
3번째 줄부터는 M개의 줄에 합을 구해야 하는 구간 i와 j가 주어진다.  

#### 출력
총 M개의 줄에 입력으로 주어진 i번째 수에서 j번째 수까지의 합을 출력한다.

### 활용공식
```JAVA
//(누적)합배열 공식
S[i] = S[i-1] + A[i]

//구간 합 공식
S[j] - S[i-1]
```

```JAVA
public class Main {

	public static void main(String[] args) throws IOException {
        //BufferedReader클래스 선언
        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(System.in)); 
        //StringTokenizer클래스 선언
        StringTokenizer stringTokenizer = new StringTokenizer(br.readLine());


        //suNo = N (수의 개수)
        int suNo = Integer.parseInt(stringTokenizer.nextToken());
        //quizNo = M(덧셈 횟수)
        int quizNo = Integer.parseInt(stringTokenizer.nextToken());
        //첫번째 줄 완성

        //정수형 타입 중 가장 큰 타입(8byte)
        long[] S = new long[suNo+1];
        stringTokenizer = new StringTokenizer(bufferedReader.readLine());


        for(int i=1; i<=suNo; i++){
            S[i] = S[i-1]+Integer.parseInt(stringTokenizer.nextToken());
        }

    }
}
```