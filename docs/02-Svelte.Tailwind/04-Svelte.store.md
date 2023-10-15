Svelte store 用于跨组件状态共享，可以使用它在组件之间传递参数值。

在 Store 中定义的变量，可以被多个组件使用；一个 Store 变量的改变，也可以通过 subscribe 机制，实时反馈给组件。



## Store注册与更新

Store写法只需要写在一个js文件中，然后通过svelte/store中提供的writable方法来向公共仓库中注册一个值作为一个仓库元素，之后在组件内可以通过subscribe来监听仓库元素的变化（理解上来说本质上是一个发布订阅的模式），通过set和update来发布仓库内某一个值的变化。

- Set 直接将仓库内的某个数指定为某个值
- Update 接收一个仓库当前值的参数的回调函数，将执行结果作为要更新仓库参数的值


## 参考

这个系列的文章很好：[Svelte 從小白到入門（六）Store](https://editor.leonh.space/2021/svelte-quickstart-6/)

[Working with Svelte stores](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Svelte_stores)


