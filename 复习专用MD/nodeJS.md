## node js  npm   gulp 包的管理

下载 npm  install  // uninstall pip maven

node js 特点  单线程（single  thread）2 非阻塞式 3事件池

## 模块化

 一个js文件就是一个common js模块  .js    .json  .node  c++ 都是一个common js模块

**模块输出**：模块只有一个出口  module.exports对象  我们需要把模块希望输出的的内容放入该对象

加载模块： 记载模块使用require 方法 该方法读取一个文件执行，返回文件内部module.exports

exports.a = 1；== let  a = 1；



## NoSQL数据库的四大分类

1 哈希值   键值对方式  典型代表  Redis   

2 列存储数据库  典型代表 HBase  

3 文档型数据库    典型代表 MongoDB

4 图形（Graph）数据库   典型代表  Neo4j

## MongoDB

###数据库操作

db  查看当前在哪个数据库

show db  查看全部数据库

use 数据库名  ：如果有 就进入当前数据库  如果没有 就先创建 在进入

db.dropDatabase() 删除数据库

### 集合操作

**创建集合** 

1    db.createCollection(name,options) 第二个参数可不写

2    db.集合名字({})

show collections  查看集合

db.createCollection("name",{capped:true,autoIndexId:true,size:1024,max:10000})  创建固定集合

删除集合   db.集合名字.drop();

修改集合名字   db.集合名字.renameCollection("新的集合	名字")

查看当前数据库中的所有集合  show collections

### 文档操作（document）

添加文档   db.集合名字({})

# nodejs 连接MongoDB

