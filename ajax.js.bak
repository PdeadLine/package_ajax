function createXMLHttpRequest(){
	try{
		return new XMLHttpRequest();  //支持FireFox等大多数浏览器
	}catch(e){
		try{
			return new ActvieXObject("Msxml2.XMLHTTP"); //支持IE6.0
		}catch(e){
			try{
				return new ActvieXObject("Microsoft.XMLHTTP");//支持IE5.0及以下版本
			}catch(e){
				alert("哥们，你用的浏览器不支持ajax!!!");
				throw e;			
			}		
		}
	}
	
}
/*
option对象有如下属性
/*请求参数 /method,
	/*请求url /url,
	/*是否异步/asyn,
	/*请求体/params,
	/*回调函数/callback,
	/*服务器响应数据转换成什么类型/type
*/
function ajax(option){
	/*
		1.得到xmlHttp
	*/
	var xmlHttp = createXMLHttpRequest();
	/*
		2.打开连接
	*/
	if(!option.method){//默认为GET请求
		option.method="GET";
	}
	if(option.asyn== undefined){//默认为异步
		option.asyn=true;
	}
	xmlHttp.open(method,url,asyn);
	//判断是否为post请求
	if(method=="post"){
		xmlHttp.setRequestHeader("Content-Type","application/x-www.form-urlencoded");
	}
	//发送请求
	xmlHttp.send(params);
	//注册监听
	xmlHttp.onreadystatechange = function(){
		if(xmlHttp.readystate==4 && xmlHttp.status==200){
			var date;
			//获取服务器的响应数据，进行转换
			if(!option.type){//默认为text;
				data = xmlHttp.responseText;
			}else if(type == "xml"){
				data = xmlHttp.responseXML;
			}else if(type =="text"){
				data == xmlHttp.responseText;
			}else if(type == "json"){
				var text = xmlHttp.responseText;
				data eval("("+text+")");
			}

			callback(data);
		}
	}

}