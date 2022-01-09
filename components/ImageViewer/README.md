# H5图片查看器
### 场景
最近需求涉及到图片查看的操作，UI设计了一张图片查看的图，要求点击查看图片并支持左右滑动，由于antd-mobile v2版本没有类似组件，所以通过套娃的方式套一个。
            套娃结果：UI还是挺满意😂😂。

[查看地址](https://www.csdn.net/)

### 依赖
antd-mobile@2.3.4
## 预览图
![在这里插入图片描述](https://img-blog.csdnimg.cn/9c06b7deac664c73adca0f074376dad8.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5ZCD57OW55qE5LmU5be0,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center =375x667)


### 套娃流程
 - 首先通过 Modal 来实现查看的遮罩 
 - 接着在 Modal 里面套一个 Carousel 用来显示图片
 - 最后在 Carousel 中布局，实现交互效果
 - 注：需要修改组件本身的css
	
### 使用
 1. 数据源
 ```javascript
const demoImages = [
	  {
	    url:
	      "https://images.unsplash.com/photo-1620476214170-1d8080f65cdb?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=3150&q=80",
	    title: "楼层",
	    describe: "楼层楼层楼层"
	  },
	  {
	    url:
	      "https://images.unsplash.com/photo-1601128533718-374ffcca299b?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=3128&q=80",
	    title: "风景",
	    describe: "风景风景风景风景风景风景风景"
	  },
      // ...
];
```

 2. 组件
  ```javascript
	<ImageViewer
        visible={boolean}
        selectedIndex={1}
        images={demoImages}
        onClose={() => {
         
        }}
      />
```




3. 参数
 
| 属性 | 说明 | 类型|默认值|
|--|--|--|--|
|  images|图片资源的 url 列表  |[]|-|
|  visible|是否显示  |boolean|false|
|  selectedIndex|默认显示第几张图片  |number|0|
|  onClose|关闭触发  |(false) => void|-|

### 总结
功能算是实现了，整个组件封装的过程也是对知识点的回顾
- 管理组件状态 useState
- 执行副作用 useEffect
- 负责缓存优化 useMemo











