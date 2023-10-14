
## 传值给子组件

在子组件中导出变量：

```
<script>
  export let propValue
</script>

<p>I'm taking this from the parent: {propValue}</p>
```

然后在父组件中传值给子组件：

```
<script>
  import Child from './Child.svelte'
</script>

<Child propValue="Pass this to the child!" />
```


来源：[Passing props down to a child](https://svelte.dev/repl/b350218ccfa146fca65e766f05dfd235?version=3.38.2)

