# study
html5
一个关于前端的博客：http://www.cnblogs.com/jr1993/p/4598630.html
一个关于订单进度条的制作：
<style>
#progressBar{
            width: 80%;
            height: 50px;
            position: relative;
            margin: 50px 0 0 100px;
        }
        #progressBar div{
            width: 100%;
            height: 10px;
            position: absolute;
            top:50%;
            left: 0;
            margin-top:-20px;
            background: #ccc;
        }
        #progressBar div span{
            position: absolute;
            display: inline-block;
            background: green;
            height: 10px;
            width: 100%;
            -webkit-animation:bgLoad 13s linear;
        }
        @-webkit-keyframes bgLoad{
            0%{
                width: 0%;
            }
            7.68%,11.52%{
                width:11%;
            }
            19.2%,23.04%{
                width: 22%;
            }
            30.72%,34.56%{
                width: 33%;
            }
	    42.24%,46.08%{
                width: 44%;
            }
	    53.76%,57.6%{
                width: 55%;
            }
            65.28%,69.72%{
                width: 66%;
            }
            76.8%,80.64%{
                width: 77%;
            }
            88.32%,92.16%{
                width: 88%;
            }
            100%{
                width:100%;
            }
        }
        #progressBar>span{
            position: absolute;
            top:0;
            margin-top: -10px;
            width: 40px;
            height: 40px;
            border-radius: 50%;      //圆的形成 
            background: #ccc;
            margin-left: -20px;
            color:#fff;
        }
        @-webkit-keyframes circleLoad_1{
            0%,66.66%{
                background: #ccc;   //线条从0到66.66之间颜色都不会发生改变66.66之后开始发生改变，到100的时候为另一个完全的颜色，下面是一样的
           }
                 100%{
                background:green;
            }
        }
        @-webkit-keyframes circleLoad_2{
            0%,83.34%{
                background: #ccc;
            }
            100%{
                background:green;
            }
        }
        @-webkit-keyframes circleLoad_3{
            0%,88.88%{
                background: #ccc;
            }
            100%{
                background:green;
            }
        }
        @-webkit-keyframes circleLoad_4{
            0%,91.67%{
                background: #ccc;
            }
            100%{
                background:green;
            }
		}
        #progressBar span:nth-child(2){   第一个圆圈开始
            left: 0%;background:green;
        }
        #progressBar span:nth-child(3){
            left: 11%;background:green;
            -webkit-animation:circleLoad_1 1.5s ease-in;
        }
        #progressBar span:nth-child(4){
            left: 22%;background:green;
            -webkit-animation:circleLoad_2 3s ease-in;
        }
        #progressBar span:nth-child(5){
            left: 33%;background:green;
            -webkit-animation:circleLoad_3 4.5s ease-in;
        }
        #progressBar span:nth-child(6){
            left: 44%;background:green;
            -webkit-animation:circleLoad_4 6s ease-in;
        }
	#progressBar span:nth-child(7){
            left: 55%;background:green;
            -webkit-animation:circleLoad_4 7.5s ease-in;
        }
	#progressBar span:nth-child(8){
            left: 66%;background:green;
            -webkit-animation:circleLoad_4 9s ease-in;
        }
	#progressBar span:nth-child(9){
            left: 77%;background:green;
            -webkit-animation:circleLoad_4 10.5s ease-in;
        }
	#progressBar span:nth-child(10){
            left: 88%;background:green;
            -webkit-animation:circleLoad_4 12s ease-in;
        }
	#progressBar span:nth-child(11){
            left: 100%;background:green;
            -webkit-animation:circleLoad_4 13.5s ease-in;
        }
     
</style>
<div id="progressBar">
     <!-- 进度条 -->
     <div>
         <span></span>
     </div>
     <!-- 10个圆 -->
     <span></span>
     <span></span>
     <span></span>
     <span></span>
     <span></span>
     <span></span>
     <span></span>
     <span></span>
     <span></span>
     <span></span>
</div>

说明：这个进度条，设置的是走一段用时一秒，然后每到一个圆点就停顿0.5秒，而这0.5秒就是相对应的圆点的动画持续执行时间；
细长条的动画持续时间通过计算：9小段*1秒+中间8个圆点*0.5秒=13秒。
接下来就是计算细长动画关键帧的时间分配，设每一份0.5秒，那么总共就是26份，每个小段得2份，每个圆点得1份，用100除以26，每份大约是3.84%
，接下来就是分配时间了。


@-webkit-keyframes labelON{
0%{
top:0px;
left:0px;
}
100%{
top:0px;
left:38px;
}
}

@keyframes(关键帧)作为CSS3动画的一部分，其该紧跟一个标识符(由开发者自定)，此标识符将在其他CSS代码中引用。在@keyframes和标识符之后，就是一系列的动画规则(就像普通的CSS代码中声明的style规则)了。这一系列动画规则用大括号括起来隔开，然后再嵌在@keyframes之后的大括号里，类似其他@语法规则.
以楼主贴出的代码为例，前缀(the vendor prefixes)webkit表示这个动画效果只适用于webkit内核的浏览器，labelON就是这个动画里面关键帧的名字(animation-name)。0%和100%表示这个动画从开始到结束，向右移动了38px(top值不变，left值增加到38px)。

进度条的三种方式：https://www.cnblogs.com/iqian/p/6825084.html


关于巡检的内容：
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN"> 
<html> 
    <head> 
        <title>点击文字弹出一个DIV层窗口代码</title> 
        <style> 
        .black_overlay{ 
            display: none; 
            position: absolute; 
            top: 0%; 
            left: 0%; 
            width: 100%; 
            height: 100%; 
            background-color: black; 
            z-index:1001; 
            -moz-opacity: 0.8; 
            opacity:.80; 
            filter: alpha(opacity=88); 
        } 
        .white_content { 
            display: none; 
            position: absolute; 
            top: 25%; 
            left: 25%; 
            width: 55%; 
            height: 55%; 
            padding: 20px; 
            border: 10px solid green; 
            background-color: white; 
            z-index:1002; 
            overflow: auto; 
        } 
#progressBar{
            width: 80%;
            height: 50px;
            position: relative;
            margin: 50px 0 0 100px;
        }
        #progressBar div{
            width: 100%;
            height: 10px;
            position: absolute;
            top:50%;
            left: 0;
            margin-top:-20px;
            background: #ccc;
        }
        #progressBar div span{
            position: absolute;
            display: inline-block;
            background: green;
            height: 10px;
            width: 100%;
            -webkit-animation:bgLoad 5.5s linear;
        }
@-webkit-keyframes bgLoad{
            0%{
                width: 0%;
            }
            18.18%,27.27%{
                width:25%;
            }
            45.45%,54.54%{
                width: 50%;
            }
            72.72%,81.81%{
                width: 75%;
            }
            100%{
                width:100%;
            }
        }
#progressBar>span{
            position: absolute;
            top:0;
            margin-top: -10px;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: #ccc;
            margin-left: -20px;
            color:#fff;
        }
@-webkit-keyframes circleLoad_1{
            0%,50%{
                background: #ccc;
            }
            100%{
                background:green;
            }
        }
        @-webkit-keyframes circleLoad_2{
            0%,60%{
                background: #ccc;
            }
            100%{
                background:green;
            }
        }
        @-webkit-keyframes circleLoad_3{
            0%,70%{
                background: #ccc;
            }
            100%{
                background:green;
            }
        }
        @-webkit-keyframes circleLoad_4{
            0%,90%{
                background: #ccc;
            }
            100%{
                background:green;
            }
        }
        #progressBar span:nth-child(2){
            left: 0%;background:green;
        }
        #progressBar span:nth-child(3){
            left: 25%;background:green;
            -webkit-animation:circleLoad_1 1.5s ease-in;
        }
        #progressBar span:nth-child(4){
            left: 50%;background:green;
            -webkit-animation:circleLoad_2 3s ease-in;
        }
        #progressBar span:nth-child(5){
            left: 75%;background:green;
            -webkit-animation:circleLoad_3 4.5s ease-in;
        }
        #progressBar span:nth-child(6){
            left: 100%;background:green;
            -webkit-animation:circleLoad_4 6s ease-in;
        }
    </style> 
    </head> 
    <body> 
        <p>示例弹出层：<a href = "javascript:void(0)" onclick = 

"document.getElementById('light').style.display='block';document.getElementById

('fade').style.display='block'">请点这里</a></p> 
        <div id="light" class="white_content">正在巡检..........
<div id="progressBar">
      <!-- 进度条 -->
      <div>
        <span></span>
      </div>
      <!-- 五个圆 -->
      <span></span>
      <span></span>
      <span></span>
      <span></span>
      <span></span>
 </div> 
<a href = "javascript:void(0)" onclick = "document.getElementById

('light').style.display='none';document.getElementById('fade').style.display='none'">点

这里关闭本窗口</a></div> 
        <div id="fade" class="black_overlay"></div> 
    </body> 
</html>


