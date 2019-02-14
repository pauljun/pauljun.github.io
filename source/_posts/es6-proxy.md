# es6 Proxy
Proxy 用于修改某些操作的默认行为,等同于在语言层面做了修改。Proxy在目标对象之前做了架设一层拦截, 外界访问该对象, 必须先通过这层拦截, 因此提供了一种机制, 可以对外界的访问进行过滤和改写。

<!--more -->

## Proxy支持的拦截一共有十三种:

### 1.get 

```
var obj = {
  name: "get"
};

var proxy = new Proxy(obj, {
  get: function(target, key, receiver) {
    if (key in target) {
      return Reflect.get(target, key, receiver);
    } else {
      return null
    }
  }
})

console.log(proxy.name)   //'get'
console.log(proxy.age)    //null
```



- 拦截对象属性的读取,比如proxy,foo 和proxy['foo']

### 2.set

``````
var obj = {
  name: ""
};

var proxy = new Proxy(obj, {
  set: function(target, key, value, receiver) {
    if (key in target) {
      return Reflect.set(target, key, value, receiver);
    } else {
      console.error(`proxy对象 不存在${key}属性, 写入失败`)
      return null
    }
  }
})

proxy.name = 'set'
console.log(proxy)  //{name: 'set'}
proxy.title = 'set' //proxy 对象不存在title属性,写入失败
console.log(proxy)  //{name: 'set'}
``````

- 拦截对象属性的设置, 比如`proxy.foo = v`或`proxy['foo'] = v`返回一个值

### 3.apply

```
apply: function(target, object, args){
    
}
```



- 拦截Proxy实例作为函数调用的操作,比如`proxy(...args)`、`proxy.call(object, ...args)`、`proxy.apply(...)`

### 4.construct

```
construct: function(target, args){
    
}
```



- 拦截Proxy实例作为构造函数调用的操作,比如`new proxy(...args)`

### 5.has

```
has: function(target, key){
    
}
```

