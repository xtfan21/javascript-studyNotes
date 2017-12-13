对象
===
>对象是Javascript的基本数据类型，对象常用的方法是创建、设置、查找、删除、检测、枚举
## 对象的创建
 + var obj ={}
 + var obj = new Object();
 + var obj = Object.create(proto,{propertiesObject})
						proto 一个对象，作为新创建对象的原型。    
						propertiesObject  可选     
						var o1 = Object.create(null) //o1不继承任何属性与方法，创建没有原型的新对象     
						var o1 = Object.create(Object.prototype) //创建新对象     
### 属性访问错误
+ 如果obj找个对象没有name属性，那么访问obj.name就会报undefined，var len = obj.name.length很明显会抛出异常undefined没有length;                         建议写法 ： var len = obj && obj.name && obj.name.length
### 删除属性(delete)
1、用法：delete obj.name   <br/>
2、delete只是断开属性和宿主对象的关系，而不会操作属性中的属性<br/>
    比如：var obj={"a":{'name':1}};<br/>
    var del=obj.a   //{'name':1}<br/>
    delete obj.a;<br/>
    console.log(del.name);  //1<br/>
