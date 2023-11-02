

[How to refresh app post deploy](https://github.com/sveltejs/kit/discussions/8665#discussioncomment-4760788)

采用上面的方法，实际代码（+layout.svelte）：

```
<script>
	import Header from './Header.svelte';
	import './styles.css';
	import { updated } from '$app/stores';
</script>

<div class="app" data-sveltekit-reload={$updated ? "" : "off"}>
	<slot />
</div>
```



