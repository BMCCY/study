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
            border-radius: 50%;
            background: #ccc;
            margin-left: -20px;
            color:#fff;
        }
        @-webkit-keyframes circleLoad_1{
            0%,66.66%{
                background: #ccc;
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
        #progressBar span:nth-child(2){
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
