``` html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>显示时钟</title>
		<script>
			var hours,hello,minus,secos,msecs,years,mouts,dayss,lates,yours;
			var texts,times,dates,weeks;
			function gain(){
				//实例化一个日期对象
				var today = new Date();
				//得到当前的小时
				hours=today.getHours()<10?'0'+today.getHours():today.getHours();
				//得到当前的分钟
				minus=today.getMinutes()<10?'0'+today.getMinutes():today.getMinutes();
				//得到当前的秒钟
				secos=today.getSeconds()<10?'0'+today.getSeconds():today.getSeconds();
				//得到当前的毫秒
				msecs=today.getMilliseconds()<10?'00'+today.getMilliseconds():today.getMilliseconds()<100?'0'+today.getMilliseconds():today.getMilliseconds();
				//得到当前的年份
				years=today.getFullYear()<0?'0'+today.getFullYear():today.getFullYear();
				//得到当前的月份
				mouts=(today.getMonth()+1)<10?'0'+(today.getMonth()+1):(today.getMonth()+1);
				//得到当前的日期
				dayss=today.getDate()<10?'0'+today.getDate():today.getDate();
				//得到当前的周几
				weeks=today.getDay()==0?'周日':today.getDay()==1?'周一':today.getDay()==2?'周二':today.getDay()==3?'周三':today.getDay()==4?'周四':today.getDay()==5?'周五':'周六';
				//得到当前的问候
				hello=(hours>0&&hours<=5)?'凌晨好':(hours>5&&hours<=7)?'早上好':(hours>7&&hours<=11)?'上午好':(hours>11&&hours<=13)?'中午好':(hours>13&&hours<=16)?'下午好':(hours>16&&hours<=18)?'傍晚好':(hours>18&&hours<=21)?'晚上好':(hours>21&&hours<=23)?'深夜好':'午夜好';
				
				texts='~大家'+hello+'~';
				dates=years+' - '+mouts+' - '+dayss+' - '+weeks;
				times=hours+':'+minus+':'+secos;
				lates='~ Happy every day ~';
				yours='~ 欢迎 随时 @ me , 有时间 会 逐一 回复 ~ ';
			}
			function changcolor(key,ze){
				var color='';
				var result='';
				if (ze=='china') {
					for(var i=0;i<key.length;i++){
						color='#'+Math.ceil(Math.random()*16777215).toString(16);
						result+='<font color='+color+'>'+key.substring(i,i+1)+'</font>';
					}
				}
				if (ze=='english') {
					var keys= key.split(' ');
					for (var i = 0; i <keys.length; i++) {
						color='#'+Math.ceil(Math.random()*16777215).toString(16);
						result+='<font color='+color+'>'+keys[i]+' </font>';
					}
				}		
				return result;
			}
			function show(){
				var textc=document.getElementById("text").innerHTML=changcolor(texts,'china');
				var datec=document.getElementById("date").innerHTML=changcolor(dates,'english');
				var timec=document.getElementById("time").innerHTML=changcolor(times,'china');
				var txtac=document.getElementById("txta").innerHTML=changcolor(lates,'english');
				var txtbc=document.getElementById("txtb").innerHTML=changcolor(yours,'english');
				var co1os=document.getElementById("co1o").innerHTML=jiequ(colorsno(texts,textc));
				var co2os=document.getElementById("co2o").innerHTML=jiequ(colorsno(dates,datec));
				var co3os=document.getElementById("co3o").innerHTML=jiequ(colorsno(times,timec));
				var co4os=document.getElementById("co4o").innerHTML=jiequ(colorsno(lates,txtac));
				var co5os=document.getElementById("co5o").innerHTML=jiequ(colorsno(yours,txtbc));	
	
			}
			function english(key){
				var result='';
				
				result
			}
			function jiequ(key){
				var result='';
				var color= key.split(',');
				for(var i=0;i<color.length;i++){
					result+='<font color='+color[i]+'>'+color[i]+'		'+'</font>';
				}
				return result;
			}
			function colorsno(vlengths,values){
				var i=0,j=0,s=0,beg,end,result='';
				for(s=0;s<vlengths.length;s++){
					for(i;i<values.length&&values.charAt(i)!="#";i++);
					for(j=i;j<values.length&&values.charAt(j)!=">";j++);
					if(s<vlengths.length-1){
						result+=values.substring(i,j)+',';
					}else{
						result+=values.substring(i,j);
					}
					i=j;
				}
				return result;
			}
			function starts(){
				gain();
				show();				
				//第一个参数是所要调用的方法
				//第二个是每隔多少毫秒执行一次这个函数
				setTimeout('starts()',1000);
			}
		</script>
	</head>
	<body onload="starts()">
		<form method="post" name="myform" action="#"  >
			<h1><label id="text"></label></h1>
			<h3><label id="co1o"></label></h3>
			<h1><label id="date"></label>&nbsp;&nbsp;<label id="week"></label></h1>
			<h3><label id="co2o"></label></h3>
			<h1>&nbsp;&nbsp;<label id="time"></label>&nbsp;&nbsp;<label id="msms"></label></h1>
			<h3><label id="co3o"></label></h3>
			<h1><label id="txta"></label></h1>
			<h3><label id="co4o"></label></h3>
			<h1><label id="txtb"></label></h1>
			<h3><label id="co5o"></label></h3

			
		</form>	
	</body>
</html>
```

