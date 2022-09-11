# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题

**加粗**
*斜体*
***斜体加粗***
~~删除线~~
++下划线++


一级标题
====
一级标题
=
二级标题
---------------

>引用
>>引用
>>>>>>>>引用

---
***
*************
--------

![哈哈哈](https://b-ssl.duitang.com/uploads/item/201611/12/20161112143109_kGjWM.jpeg "aaaaaaaa")

[百度](www.baidu.com "也一样")
- 刘备
+ 丈夫
* 三店
1. 三店
2. 到付
3. 人
- 一级
  - 二级
     2. 三级
        2. 四级
          - 到付
            7. 顺丰
            8. 
- 色粉

===

ef|re|ds 
:---|---:|:---:
d |f |sdf
drgdrg靠左 |dfgddgdgfgd靠右|dfgdgh居中

`牛B的代码`

```
ew 
wf  ;ef 
  sef ;
  许多行牛B的代码
```

```mermaid
graph LR
    a
    b[This is the text in the box]
    c(This is the text in the box)
    d((This is the text in the circle))
    e>This is the text in the box]
    f{This is the text in the box}
    g["This is the (text) in the box"]
```

```mermaid
graph LR;
    A1-->B1
    A2---B2
    A3--This is the text---B3
    A4---|This is the text|B4
    A5-->|text|B5
    A6-- text -->B6
    A7-.->B7
    A8==>B8
    A9== text ==>B9
    A10["A double quote:#quot;"] -->B10["A dec char:#9829;"]
```
```mermaid
gantt
　　　dateFormat　YYYY-MM-DD
　　　title Adding GANTT diagram functionality to mermaid
　　　section A section
　　　Completed task　　:done, des1, 2014-01-06,2014-01-08
　　　Active task 　　　　:active, des2, 2014-01-09, 3d
　　　future task 　　　　:　　　  des3, after des2, 5d
　　　future task2　　　　:　　　  des4, after des3, 5d
　　　section Critical tasks
　　　Completed task in the critical line　:crit, done, 2014-01-06,24h
　　　Implement parser and json　　　　　　:crit, done, after des1, 2d
　　　Create tests for parser　　　　　　　:crit, active, 3d
　　　Future task in critical line　　　　　:crit, 5d
　　　Create tests for renderer　　　　　　:2d
　　　Add to ,mermaid　　　　　　　　　　　:1d
```

```mermaid
sequenceDiagram
　　　participant Alice
　　　participant Bob
　　　Alice->John:Hello John, how are you?
　　　loop Healthcheck
　　　　　John->John:Fight against hypochondria
　　　end
　　　Note right of John:Rational thoughts <br/>prevail...
　　　John-->Alice:Great!
　　　John->Bob: How about you?
　　　Bob-->John: Jolly good!

```

```mermaid
sequenceDiagram
    A->>B: 是否已收到消息？
    B-->>A: 已收到消息
```

