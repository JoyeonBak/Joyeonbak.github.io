---
layout: post
title: "[Markdown] Manual"
subtitle: 
categories: Markdown
tags: [Markdown]
--- 
### 색상
<span style="color: red">red</span>
<span style="color: #0000FF">파랑</span>
<span style="color: #008000">초록</span>
<span style="color: #2D3748; background-color:#fff5b1;"> Strong</span>
<span style="color: #808080">그레이</span>
<span style="color: #ffd33d">노랑</span>


```PYTHON
<span style="color: red">red</span>
<span style="color: #0000FF">파랑</span>
<span style="color: #008000">초록</span>
<span style="color: #2D3748; background-color:#fff5b1;"> Strong</span>
<span style="color: #808080">그레이</span>
<span style="color: #ffd33d">노랑</span>
```

### 형광펜
<span style='background-color: #fff5b1'>노란형광펜</span>
<span style='background-color: #f6f8fa'>회색형광펜</span>
<span style='background-color: #f1f8ff'>파랑형광펜</span>
<span style='background-color: #ffdce0'>빨강형광펜</span>
<span style='background-color: #dcffe4'>초록형광펜</span>
<span style='background-color: #f5f0ff'>보라형광펜</span>
<span style='background-color: #F7DDBE'>주황형광펜</span>


```PYTHON
<span style='background-color: #fff5b1'>노란형광펜</span>
<span style='background-color: #f6f8fa'>회색형광펜</span>
<span style='background-color: #f1f8ff'>파랑형광펜</span>
<span style='background-color: #ffdce0'>빨강형광펜</span>
<span style='background-color: #dcffe4'>초록형광펜</span>
<span style='background-color: #f5f0ff'>보라형광펜</span>
<span style='background-color: #F7DDBE'>주황형광펜</span>
```

### 이미지 사이즈 조정
이미 css에 지정되어있으면, 마크다운에서 작성한 내용이 반영되지 않을 수 있음


```PYTHON
## 마크다운
# 사이즈 직접지정 (px)
![title](/imges/img.png){: width="100" height="100"}
# (차지할 수 있는) 전체범위의 몇퍼센트를 차지할 지 
![title](/imges/img.png){: width="100%" height="100%"}
```