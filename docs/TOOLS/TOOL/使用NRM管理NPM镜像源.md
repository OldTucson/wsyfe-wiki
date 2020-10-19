---
title: 使用NRM管理NPM镜像源
---

平时我们在使用npm安装包时介于网络原因通常会将镜像源切换成淘宝的
```js
​​​​​​​npm config set registry=http://registry.npmjs.org
```

但这样做既麻烦又没有可读性 故我们可以使用nrm来管理

### 安装

```js
npm install -g nrm

```

### 查看镜像源列表

```js
nrm ls
```
![查看](/nrm0.png)

### 选择使用

```js
nrm use taobao
```
![使用](/nrm2.png)
![使用](/nrm1.png)

