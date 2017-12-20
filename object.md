对象
===
>对象是Javascript的基本数据类型，对象常用的方法是创建、设置、查找、删除、检测、枚举

## 对象的创建

> 三种创建方法：
```javascriptvar 
 1、 var obj ={}
 2、 var obj = new Object();
 3、 var obj = Object.create(proto,{propertiesObject})
        参数说明:
	proto 一个对象，作为新创建对象的原型。  如果参数不是null或者对象，将会抛出异常  
	propertiesObject  可选
						
	var o1 = Object.create(undefined) //报错
	var o1 = Object.create(null) //o1不继承任何属性与方法，创建没有原型的新对象
	var o1 = Object.create(Object.prototype) //创建新对象  =  Object.create({})
	var obj5 = Object.create({a:444},{
	foo: {
	    configurable: false,   //是否能删除   默认false
	    writable: false,  //是否能修改属性值   默认false 不可修改
	    value: 'hello'
	}
	});
	obj5.foo = 'me';
	console.log(obj5.foo); //hello
	console.log(obj5.__proto__); //{a:444}
```

### 属性访问错误

+ 如果obj找个对象没有name属性，那么访问obj.name就会报undefined，var len = obj.name.length很明显会抛出异常undefined没有length;<br />
  建议写法 ： var len = obj && obj.name && obj.name.length

### 删除属性(delete)
1、用法：delete obj.name   <br/>
2、delete只是断开属性和宿主对象的关系，而不会操作属性中的属性<br/>

```javascript
    var obj={"a":{'name':1}};
    var del=obj.a   //{'name':1}
    delete obj.a;
    console.log(del.name);  //1
```

### 遍历属性
1、for/in
> 遍历可枚举的实例属性和继承属性
```javascript
    var po = {a:1,b:2};
    var o2 = {c:3,d:4};
    o2.__proto__ = po;
    for(key in o2){
        console.log(key);//c,d,a,b
    }
```
2、Object.keys(obj)
> 返回数组，包含可枚举的实例属性名称
```javascript
    var po = {a:1,b:2};
    var o2 = {c:3,d:4};
    o2.__proto__ = po;
    var o3 = Object.keys(o2);
    console.log(o3); //[c,d]
```

