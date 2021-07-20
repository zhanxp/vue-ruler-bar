# vue-ruler-bar
> 基于vue 2.x的 刻度尺，只支持移动端
## 实例代码：
```
    体重
    <DLRuler :value="50" :min="30" :max="300" :onChange="changeWeight"></DLRuler>
    身高
    <DLRuler :value="60" :min="10" :max="100"></DLRuler>
    测试
    <DLRuler :value="35" :min="10" :max="120"></DLRuler>
```    
参数描述：

value 当前值

min 最小值

max 最大值

change：数值发生改变后调用， 可选参数

## 效果：
![image](https://github.com/zhanxp/vue-ruler-bar/blob/master/ruler.gif)
## 问题：
最小刻度还有bug,

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run start
```

### Compiles and minifies for production
```
npm run build
vue-cli-service build --target lib --dest vue-ruler --name DLRuler src/components/DLRuler.vue
vue-cli-service build --target lib --dest vue-nrs-bar --name NrsBar src/components/NrsBar.vue
vue-cli-service build --target lib --dest vue-nut-bar --name NutBar src/components/NutBar.vue
```
