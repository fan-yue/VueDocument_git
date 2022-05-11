## el的两种写法

### new Vue 时候配置el属性

默认写法

```
<script>
      const v = new Vue({
          el:'#a',
          data:{
              name:'名字'
          }
      })
</script>
```



### 通过 vm.$mount('#a') 执行

先创建 Vue实例，然后在通过 vm.$mount('#a') 执行el的值

```
    <script>
        const v = new Vue({
            data:{
                name:'名字'
            }
        })
        v.$mount('#a');
    </script>
```



## data的两种写法

在学习组件时，data必须使用函数式，否则会报错

### 对象式

```
    <script>
        const v = new Vue({
            el:"#a",
            data:{
                name:'名字',
                age:18
            }
        })
    </script>
```



### 函数式

#### 	第一种写法

```
    <script>
        const v = new Vue({
            el:"#a",
            data:function(){
                return{
                    name:'姓名',
                    age:18
                }
            }
        })
    </script>
```

#### 	第二种写法

​	不包含**function**

```
    <script>
        const v = new Vue({
            el:"#a",
            data(){
                return{
                    name:'姓名',
                    age:18
                }
            }
        })
    </script>
```

