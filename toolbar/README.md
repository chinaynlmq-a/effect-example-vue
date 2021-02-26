# toolbar

## Project setup
```
 cd toolbar
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

### 需求：
顶部导航随着向下滑动隐藏，向上滑动显示，带有动画效果，一比较自然的现象展示，
  如：csdn 当移动端头部
###  技术需求分析：
1. 布局 在移动端顶部展示
2. 监听滑动效果，方向的判断
3. 向下滑动一段距离开始隐藏头部
4. 向上滑动如果头部已经隐藏展示出来
5. 向上或者向下编写动画效果，展现友好一点  

### 技术实现方案

 1. 布局固定在顶部使用css3属性：position: fixed;
 2. 监听滑动通过JavaScript，window对象中的srcoll滚动事件监听
 3. 通过记录滚动最后位置和当前记录位置对比是向上还是向下通过if判断
 4. 动画效果依据上下的放心添加class 通过 transform transition 来控制显示和动画效果

 

