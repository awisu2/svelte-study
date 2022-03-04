# call export function

1. export function
2. bind component
3. call function with bind instance

## sample

- online code: [Call export function • REPL • Svelte](https://svelte.dev/repl/a0e10de232f242289f9718041a66651b?version=3.46.4)

## codes

App.svelte

```js
<script>
	import Hello from './Hello.svelte'

	let hello = null
	function click() {
		hello.toggle()
  }
</script>

<h1>call export function</h1>

<button type="button" on:click="{click}">toggle hello</button>
<Hello bind:this="{hello}"></Hello>
```

Hello.svelte

```js
<script>
	let isShow = true
  export function toggle() {
		isShow = !isShow
	}
</script>

{#if isShow}
Hello World!
{/if}
```
