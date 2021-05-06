## APICloud

### 1. xxx

### 2. 常见基础场景的开发

#### 2.1 打开一个新页面

```
api.openWin({name, url, pageParam});
```

#### 2.2 关闭当前页面

```
api.closeWin();
```

#### 2.3 获取新页面参数

```
const param = api.pageParam;
```

#### 2.4 页面回退时传参

在这种情况下， 通过 `openWin` 打开旧页面， 同时 `reload`属性设为 `true`, 将参数放入 `pageParam` 中。 此种情况下，旧页面被显示到最前面， 同时被重新加载。

```
function handleOk() {
	api.closeWin();
	api.openWin({name, url, pageParam, reload});
	// 或者 跨win 执行脚本
	api.execScript('winName', frameName, script);
}
```

#### 2.5 页面初始化

```
apiReady = function () {}
```

#### 2.6 组件通信

- `api.execScript` 函数

### 3.  其他场景的开发

#### 3.1 照片浏览

```
function showImg(src, isNet) {
			var photoBrowser = api.require('photoBrowser');
			if (!isNet) {
				var img_path = new Array();
				img_path = src.split('/');
				var fs = api.require('fs');
		        fs.copyTo({
		            oldPath: src,
		            newPath: 'fs://res'
		        },function(ret,err){
		            if (ret.status) {
										var fs_path= 'fs://res/'+img_path[img_path.length-1];
										photoBrowser.open({
											images : [fs_path],
											placeholderImg : 'widget://res/img/apicloud.png',
											bgColor : '#000'
										}, function(ret, err) {
											if (ret) {
												if (ret.eventType == 'click')
													photoBrowser.close();
											} else {
												alert(JSON.stringify(err));
											}
										});
		            }else {
		                console.log(err.msg);
		            };
		        });
			} else {
				src = src.replace('thumb/thumb_', '/');
				photoBrowser.open({
					images : [src],
					placeholderImg : 'widget://res/img/apicloud.png',
					bgColor : '#000'
				}, function(ret, err) {
					if (ret) {
						if (ret.eventType == 'click')
							photoBrowser.close();
					} else {
						alert(JSON.stringify(err));
					}
				});
			}
		}
```



### 4. 模块

#### 4.1 api.js

对常用 js功能的封装。 `$api.xxxx`的用法。



