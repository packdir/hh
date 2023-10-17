
## 绑定击键事件

```
<script>
	let value = '' 
	let pressed = []
	
	function handleKeydown(e) {
		 pressed = [e.key, ...pressed]
	}
</script>

Value is: {value}

<input type="number" bind:value on:keydown={handleKeydown}/>

<h2>Keys Pressed</h2>

<ul>
	{#each pressed as key}
		<li>{key}</li>
	{/each}
</ul>
```

来源：[Number input with keyDown event](https://svelte.dev/repl/bfd93b0799c142979eefa1f2558bfb96?version=3.20.1)


## 将 Enter 绑定到表单提交

```
<script>
	let value = '';
	let submittedValue = null;
</script>

<form on:submit|preventDefault={() => submittedValue = value}>
	<label>
		Search
		<input bind:value />
	</label>
	
	<button on:click={() => console.log('button clicked')}>GO</button>
</form>

{#if submittedValue != null}
	<p>Submitted: {submittedValue}</p>
{/if}

<style>
	label { display: inline; }
</style>
```

来源：[SO - Form submission example](https://svelte.dev/repl/eda7ac5b71d047fabfb626712ad00554?version=3.47.0)


## Ctrl + Enter 提交表单（JavaScript）

```
document.body.addEventListener('keydown', (event) => {
    if(event.key === "Enter" && (event.metaKey || event.ctrlKey)) {
        event.target.form?.submit();
    }
});
```

## Ctrl + Enter 提交表单（TypeScript）

```
 /**
   * @param e {KeyboardEvent}
   */
document.body.addEventListener("keydown", (e: KeyboardEvent) => {
    if (!(e.key === "Enter" && (e.metaKey || e.ctrlKey))) return

    const form = (e.target as HTMLFormElement).form
    if (form) form.submit() // or form.requestSubmit() depending on your usecase
  })
```

Line # 4 is basically a check for the existence of the form element as the target of the event. The e.target.form will yield a form if any one of the inputs within the form is focused.

So pressing Ctrl+Enter with any input or button element being focused within the form will submit the form.

