前端：微信开发工具/html+css+js
接口：每个页面需要后端提供的接口如下：

动态

	1.
		Request:
			https://www.future-algorithm.com/login
		data:
			{
			code: code, //用户标识
        		touxiang: app.globalData.avatarUrl, //用户微信头像
      		sex: app.globalData.gender,//用户性别
       		city: app.globalData.city,//居住城市
        		name: app.globalData.name//用户微信名
}
Response:{
					usrId //返回的用户ID，

}
	2. Request:
			Localhost:5000/  + 'note/recNote'


		data:
			{
				sessionKey: app.globalData.usrId//返回所有的推荐动态

}
Response:{
					totalImg //返回动态图片


}
3. Request:
			Localhost:5000/  + 'note/followNote'


		data:
			{
				sessionKey: app.globalData.usrId//返回所有的关注动态

}
Response:{
					totalImg //返回推荐动态图片


}
2.发布动态
1.Request:
			Localhost:5000/  + note/showTopic'

data:
		{
			sessionKey: app.globalData.usrId//用户的ID

}
Response:{	
				Additional//返回

}

2.Request:
			Localhost:5000/  + 'note/delete'

data:
		{
				sessionKey: app.globalData.usrId,
note_id: that.data.note_id//用户发布动态的ID
}
Response:{
					
				//返回删除成功后的发布动态页面

}


3.Request:
			Localhost:5000/  + 'note/add'

data:
		{
			sessionKey:app.globalData.usrId,
        		note_title:title,//动态标题
       		note_content:content,//动态内容
        		note_hide:0,
       		topic1:tip[0],
        		topic2:tip[1],
        		topic3:tip[2],
        		topic4:tip[3],
        		topic5:tip[4]
}
Response:{
					

note_id:res.data.note_id//返回发布成功的动态页面

}
4.文件上传API
Request:
			     url: app.globalData.urls+'note/postPic',
      			filePath: data.path[i-1],
      			name: 'pic',
formdata:
		{
			sessionKey:app.globalData.usrId,
        		note_id：
        		num://数量
        		content://内容
}
Response:{
					console.log('我是结果',re.errcode)//返回上传结果

}


我的订单：
1.Request:
			Localhost:5000/  + "returnOrder"

data:
		{
			sessionKey: app.globalData.usrId//传递用户的ID

}
Response:{
					
console.log(res)//返回请求服务器返回的用户的订单


}
2. Request:
			Localhost:5000/  + '/buy/requestRefund'

data:
		{
			sessionKey: app.globalData.usrId
order_id//订单编号
}
Response:{
					
console.log(res)//返回请求服务器订单状态

}

我的动态页面：
1.Request:
			Localhost:5000/  + 'note/myNote',


data:
		{
			sessionKey: app.globalData.usrId
}
Response:{
					
console.log(res)//返回我的动态

}
