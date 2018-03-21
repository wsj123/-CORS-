## 跨域资源共享 CORS 详解

### ajax代码、发送js原生的ajax请求
```
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<meta http-equiv="X-UA-Compatible" content="IE=edge">
	<title>跨域资源共享 CORS</title>
	<link rel="stylesheet" href="">
</head>
<body>
<script>
	var url = "http://api.adv.com/games/ltvstat/list?starttime=20180314&endtime=20180321&cid=394&appid=1000032";
	var xmlhttp;
	if (window.XMLHttpRequest)
	{// code for IE7+, Firefox, Chrome, Opera, Safari
		xmlhttp=new XMLHttpRequest();
	}else{// code for IE6, IE5
		xmlhttp=new ActiveXObject("Microsoft.XMLHTTP");
	}

	xmlhttp.onreadystatechange=function()
	{
		if (xmlhttp.readyState==4 && xmlhttp.status==200)
		{
			res =xmlhttp.responseText;
			console.log(res);
		}
	}
	xmlhttp.open("GET",url,true);
	xmlhttp.send();
</script>
<div>test</div>
</body>
</html>
```
### PHP端代码
```
header("Access-Control-Allow-Origin:http://local.10001data.com");
header("Access-Control-Allow-Credentials:true");
header("Access-Control-Expose-Headers:FooBar");
header("Content-Type:text/html;charset=utf-8");

 [原文](http://www.ruanyifeng.com/blog/2016/04/cors.html "Title")
```
