## 初识Vue

1.想让Vue工作，必须创建一个Vue实例，且要传入一个配置对象

2.root容器里的代码依然符合HTML规范，只不过深入了一些特殊的Vue语法

3.root容器里的代码被称为 【Vue模板】

4.Vue实例和容器时一一对应的

5.真实开发只有一个Vue实例，并且会配置着组件一起使用

6.{{xxx}} 中的 xxx 要写 js表达式，并且 xxx 可以自动读取到 **data** 中的所有属性

7.一旦data中的数据发生改变，那么模板中用到该数据的地方也会更新。



`例子：`

```
<!-- 准备一个容器 -->
    <div id="root">
        <h1>hello,{{name}},{{age}}</h1>
    </div>
    
    <script>
        Vue.config.productionTip = false;   //阻止 vue 在启动时生成生产提示。

        // 创建vue实例
        const x = new Vue({
            el:'#root',//el用于指定当前Vue实例为哪一个容器，值通常为css选择器字符串
            data:{      //data中用于存储容器，数据供el所指定的容器去使用，值我们先暂时写一个对象
                name:"YF",
                age:18
            }
        })
    </script>
```



## 模板语法

Vue模板语法有两大类

### 插值语法

功能：用于解析标签体内容

写法：{{xxx}} ， xxx  是 js 表达式，并且可以直接读取到 data 中的所有属性

### 指令语法

功能：用于解析标签（包括：标签属性、标签体内容、绑定事件。。。。。）

**v-bind** 可以简写成  **:**

`例子`

```
v-bind:href='xxx' 或简写 :href='xxx', xxx同样要写js表达式 , 并且可以直接读取到 data 中的所有属性
```

备注：Vue中有很多执行，且形式都是 **v-？？？** ，此处我们只学了 v-bind，后期会学习其他指令语法



`例子`

```
<div id="a">
        <a v-bind:href="baidu">百度链接</a>
        <a :href="bilbil">哔哩哔哩</a>
        <p>{{obj.a+obj.b}}</p>
    </div>

    <script>
        new Vue({
            el:'#a',
            data:{
                baidu:'http://www.baidu.com',
                bilbil:'http://www.bilbil.com',
                obj:{
                    a:1,
                    b:2
                }
            }
        })
    </script>
```



## 数据绑定

Vue中有2种数据绑定的方式：

1.单项绑定（v-bind） ：数据只能从 data 流向页面

2.双向绑定 （v-model）：数据不仅能从 data 流向页面，还可以从页面流向 data 中



**备注：**

​	1.双向绑定一般应用在表单元素上（如：input、selcet等）

​	2.v-model:value  可以简写为  v-model ，因为 v-model 默认收集的就是 value 值



`例子`

```
    <div id="a">
        单项绑定v-bind ： <input type="text" v-bind:value="biao">
        <br>
        单项简写 : <input type="text" :value="biaoj">
        <p>{{biao}}</p>
        <p>{{biaoj}}</p>
        <hr>


        双向绑定 v-model : <input type="text" v-model:value="biaovModel">
        <br>

        双向绑定简写 : <input type="text" v-model="biaoModelj">
        <p>{{biaovModel}}</p>
        <p>{{biaoModelj}}</p>
    </div>

    <script>
        new Vue({
            el:'#a',
            data:{
                biao:'表单值',
                biaoj:'单项简写',
                biaovModel:'双向绑定',
                biaoModelj:'双向绑定简写'
            }
        })
    </script>
```

