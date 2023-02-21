---
layout: post
title: "[Jquery] 기초"
subtitle: 
categories: Jquery
tags: [Jquery]
--- 
"jquery latest" 최신 버전으로 검색해서 아래와 같이 링크로 사용 
*실무에서는 개발자와 사전에 어떤 버전을 사용할지 상의 후 결정 
*브라우저(크롬)에 html파일 열어서 확인    
```HTML
<script src="http://code.jquery.com/jquery-latest.min.js"></script>
<script>
    $(document).ready(function(){
        <!-- jquery는 보통 문서가 로드된 후 사용되기 때문에 -->
        $(".btn").click(function(){
            alert("Hi~");
        })
        $(".popup_bg").click(function(){
            $(this).css({"display":"none"});
        })
        <!-- hover했을 때와 안했을때의 상태를 위해 function을 두 개 넣어준다. -->
        $(".btn").hover(function(){
            <!-- this를 사용해야 해당 클래스/아이디에만 hover가 적용 -->
            $(this).css({
                "background":"skyblue"
            });
        },function(){
             $(this).css({
                "background":"deeppink"
            });
        })
    });

    <style>
        .btn{
            width: 100px;
            height: 400px;
        }
        .popup_bg{
            position: absolute;
            top: 0;
            left: 0;
            background: rgba(25,255,255,0.7);
        }
    </style>
</script>
```

*display: none의 반대는 display: block이 아니다. 초기 설정 상태가 어떤 상태였냐에 따라 inline, flex 등으로 다르게 변경해야 레이아웃이 망가지지 않는다.
출처 :  
<https://www.youtube.com/watch?v=JzEMb5-wVIs>
