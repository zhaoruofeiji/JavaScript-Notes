# JavaScript DOM 入门
## DOM含义
#### D：document（文档）
#### O：object（对象）
#### M：Model（模型）
## DOM把文档表示成“节点树”。
#### 节点包含三个类型：元素节点、文本节点和属性节点。
### 元素节点：标签的名字就是元素的名字
eg：
`<h1>What to buy</h1>`   h1就是一个元素节点

### 文本节点：标签中包含的文本就是文本节点
eg：
`<h1>What to buy</h1>`   What to buy就是文本节点
### 属性节点：用来对元素做出更具体的描述
eg： 
` <p title="a gentle reminder">Do not forget to buy this.</p>`   title="a gentle reminder"就是它的属性节点
### 获取元素的三个方法：
1. document.getElementById("id")
返回值是一个对象（ps：文档中每一个元素都是一个对象）。

2. document.getElementsByTagName("tag")
返回值是一个数组，可以利用length属性查出这个数组里的元素个数。

   getElementsByTagName( )允许吧一个通配符作为参数，返回文档里一共有多少元素。


3. document.getElementsByClassName("class")
返回值也是一个数组。可以查找带有多个类名的元素，指定多个类名，只要在字符串参数中用**空格**分隔类名即可。

   eg:   `<li class="sale important">Milk</li>` 
   alert(document.getElementsByClassName("important sale").length);
   
   注意：
   1. 即使在元素的class属性中类名顺序是sale important，而非参数中指定的important sale，也会匹配该元素。不仅类名顺序不重要，元素带有更多的类名也没有关系。
   1. 可能在较新的浏览器里才支持这个方法，之前都是用自己的方法去实现的。搜索匹配DOM元素的方法有很多，但是真正高效的却不多。推荐阅读**Robert Nyman**的文章*The Ultimate getElementByClassName*。

### 获取和设置属性
object.getAttribute(attribute)
object.setAttribute(attribute,value)

注意：通过setAttribute( )做出修改后，通过浏览器view source选项去查看源代码的时候，看到的仍然是改变前的属性值，**这种现象源自DOM的工作模式：先加载文档的静态内容，再动态刷新，动态刷新不影响文档的静态内容。——即，对页面内容进行刷新却不需要在浏览器里面刷新页面。**

#### 这五个方法是将要编写更多DOM脚本的基石。
 