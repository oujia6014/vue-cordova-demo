# vue-cordova-demo
在vue中调用cordova第三方插件及自定义插件demo

## 详细教程
[Vue.js 使用Cordova插件,及自定义插件笔记](https://github.com/oujia6014/blog/issues/5)
### 1.安装cordova插件
```
sudo npm install
```
### 2. cd到vue项目目录
```
cd src
```
### 3. 安装vue的npm包
```
sudo npm install
```
### 4. 编译打包到cordova的www目录
```
sudo npm run build
```
### 5. 返回cordova目录
```
cd ..
```

### 5. 添加iOS平台
```
sudo cordova platform add ios
```
### 6. 如果在vue build过就要重新在cordova目录下执行
```
sudo cordova build ios
```
