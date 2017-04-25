# tab-switch
鼠标滑过切换显示效果
html
<!doctype html>
<html>
<head>
<meta charset="utf-8">
<title>大Tab切换</title>
<link href="css/样式.css" type="text/css" rel="stylesheet">
<script src="js/脚本.js" type="text/javascript"></script>
</head>

<body>
<div class="wrap">
	<div class="tit" id="tit">
		<ul>
   			<li class="select"><a href="#">詹姆斯</a></li>
    		<li><a href="#">欧文</a></li>
            <li><a href="#">杜兰特</a></li>
            <li><a href="#">哈登</a></li>
            <li><a href="#">库里</a></li>
            <li><a href="#">威少</a></li>
        </ul>
	</div> 
	<div class="content" id="content">
            <ul>
        <div class="mod" style="display:block">    
            <li>
            <img src="img/aa18972bd40735fa1447933496510fb30e24088c.jpg">
            <p>勒布朗·詹姆斯（LeBron James），1984年12月30日出生在美国俄亥俄
            州阿克伦，美国职业篮球运动员，司职小前锋，绰号“小皇帝”，效力于NBA克利夫兰骑士队。</p>
            </li>
        </div>
        <div class="mod" style="display:none">
            <li>
            <img src="img/8d5494eef01f3a2988e909439125bc315c607c1e.jpg">
            <p>凯里·欧文（Kyrie Irving），1992年3月23日出生于澳大利亚
            墨尔本，拥有美国/澳大利亚双重国籍，职业篮球运动员，司职控球后卫，效力于NBA克里夫兰骑士队。</p>
            </li>
        </div>
         <div class="mod" style="display:none">   
            <li>
            <img src="img/31.jpg">
            <p>凯文·杜兰特（Kevin Durant），男，1988年9月29日出生于美国华盛顿
            哥伦比亚特区，美国职业篮球运动员，司职小前锋，效力于金州勇士队。</p>
            </li>
        </div>
         <div class="mod" style="display:none">
            <li>
            <img src="img/3.jpg">
            <p>詹姆斯·哈登（James Harden），1989年8月26日出生于美国加利福尼亚州洛杉矶
            （ Los Angeles, California），美国职业篮球运动员，司职后卫，效力于NBA休斯顿火箭队。</p>
            </li>
        </div>
        <div class="mod" style="display:none">
            <li>
            <img src="img/5.jpg">
            <p>斯蒂芬·库里（Stephen Curry），1988年3月14日出生于美国俄亥俄州阿克伦（
            Akron, Ohio），美国职业篮球运动员，司职控球后卫，效力于NBA金州勇士队。</p>
            </li>
        </div>
        <div class="mod" style="display:none">
            <li>
            <img src="img/6.jpg">
            <p>拉塞尔·威斯布鲁克（Russell Westbrook）， 1988年11月12日出生于美国加利福尼亚州长滩
            （Long Beach, CA），美国职业篮球运动员，司职控球后卫，效力于NBA俄克拉荷马城雷霆队。</p>
            </li>
        </div>
        </ul>
    </div>
</div>    
</body>
</html>

CSS样式
@charset "utf-8";
/* CSS Document */
*{margin:0;padding:0;font-size:12px;font-family:"微软雅黑";}
.wrap{width:800px;margin:40px auto;border:1px solid #FFF;}
.tit{border:1px solid #CCC;}
.tit ul{list-style:none;overflow:hidden;}
.tit ul li{float:left;width:131px;border:1px solid #666;
	line-height:40px;height:40px;text-align:center;background-color:#09F;}
.tit ul li a{font-size:24px;}
.tit ul li a:link,.tit ul li a:visited{text-decoration:none;color:#000;}
.tit ul li a:hover,.tit ul li a:active{color:#F00;}
.tit ul li:hover,.tit ul li:active{background-color:#FFF;border-bottom:#FFF;color:#F00}
.tit:hover,.tit:active{border-bottom:1px solid #FFF;}
.tit .select{background:#FFF;border-bottom:1px solid #FFF;color:#f00;}
.content{height:250px;overflow:hidden;border:1px solid #999;}
.content ul{list-style:none;}
.content ul li{overflow:hidden;border:1px solid #FFF;margin:15px;}
.content img{float:left;width:200px;height:200px;}
.content p{font-size:20px;line-height:40px;text-indent:2em;margin-top:20px;}
.mod{margin:0px;}

JS脚本
// JavaScript Document
function $(id){
	return typeof id==='string'?document.getElementById(id):id;	
}
window.onload = function(){
	//获取鼠标滑过或点击要切换的内容\
	var titles = $('tit').getElementsByTagName('li');
	var divs = $('content').getElementsByTagName('div');
	if(titles.length!=divs.length)
		return ;
	for(var i=0;i<titles.length;i++){
		titles[i].id=i;
		titles[i].onmouseover = function(){
			//清除所有li上的className
			for(var j=0;j<titles.length;j++){
				titles[j].className='';
				divs[j].style.display='none';
				}
			//高亮显示选择的li	
		this.className = 'select';
		divs[this.id].style.display='block';	
			}
		}
	}
