# jquery-get-real-img-width
jquery获取实际图片尺寸
```html
$(function(){
	var imgSrc = $("#image").attr("src");
	getImageWidth(imgSrc,function(w,h){
		console.log({width:w,height:h});
	});
});

function getImageWidth(url,callback){
	var img = new Image();
	img.src = url;
	
	// 如果图片被缓存，则直接返回缓存数据
	if(img.complete){
	    callback(img.width, img.height);
	}else{
            // 完全加载完毕的事件
	    img.onload = function(){
		callback(img.width, img.height);
	    }
        }
	
}

作者：于坤
链接：https://www.zhihu.com/question/28733200/answer/42400792
来源：知乎
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
