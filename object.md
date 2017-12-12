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
