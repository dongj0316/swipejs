## 移动端touch事件手势封装，事件触发，需要注意的地方：
* 同时绑定事件用空格隔开
* touchEnd不会和tag、longtag、上下左右滑动事件同时触发
* touchStart始终会触发、drag位移后始终触发
* 触发tag判定时间为150毫秒内位移距离小于4
* 触发longTag判定时间为500毫秒内未抬起手指并且位移距离小于4
* 触发swipe四个方向判定时间为150毫秒内抬起手指，范围各占90度

### 支持的事件
* 'touchStart', 'swipeLeft', 'swipeRight', 'swipeUp', 'swipeDown', 'dragVertical', 'dragHorizontal', 'touchEnd', 'drag', 'tag', 'longTag'

### 使用
```
DJ.toucher('#div').on('touchStart',function(e){
    e.preventDefault();
}).on('swipeLeft',function(e){
    //left
}).on('swipeRight',function(e){
    //right
}).on('touchEnd tag longTag',function(){
    //同时绑定
})
```
