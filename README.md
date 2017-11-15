<div style="overflow: hidden;">
  <h2 style="font-size:24px;font-family: '新宋体';line-height: 30px;float:left;width:80%;">欢迎来到我的博客！骚年</h2>
  <h4 style="float: right;width:20%;">
    <a href="www.qushengkai.com" style="font-size:18px;font-family: '新宋体';line-height: 20px;">关注我</a>
  </h4>
</div>
<div style="overflow:hidden">
	<h4 style="font-size:18px;font-family: '新宋体';line-height: 20px;padding:10px 20px;">原生ajax请求</h4>
	<p style="font-size: 12px;color:#1b252e;width:80%;padding:10px 10%;">
		var Ajax={
		    get: function(url, fn) {
			// XMLHttpRequest对象用于在后台与服务器交换数据 
			var obj = new XMLHttpRequest(); 
			obj.open('GET', url, true);
			obj.onreadystatechange = function() {
			    if (obj.readyState == 4 && obj.status == 200 || obj.status == 304)
			    {
				// readyState == 4说明请求已完成
				//从服务器获得数据
				fn.call(this, obj.responseText);
			    }
		};
		obj.send();
		},
		post: function (url, data, fn) {
		  // datat应为'a=a1&b=b1'这种字符串格式，在jq里如果data为对象会自动将对象转成这种字符串格式
			var obj = new XMLHttpRequest();
			obj.open("POST", url, true);
			// 添加http头，发送信息至服务器时内容编码类型
			obj.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
			obj.onreadystatechange = function() {
			    if (obj.readyState == 4 && (obj.status == 200 || obj.status == 304)) {
				// 304未修改
				fn.call(this, obj.responseText);
			    }
			};
			obj.send(data);
		    }
		}
	</p>
</div>



