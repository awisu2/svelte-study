# rllup-plugin-svelte

rollupを利用して、ビルドを行う

- [sveltejs/rollup\-plugin\-svelte: Compile Svelte components with Rollup](https://github.com/sveltejs/rollup-plugin-svelte)
- [rollup\.js](https://rollupjs.org/guide/en/)

## hands on

```ts
yarn add --dev svelte rollup-plugin-svelte
yarn add --dev rollup @rollup/plugin-node-resolve
```

*rollup.config.js*

公式のものからはだいぶ削った(これを記述した時点でrollupを知らなかったため、割と適当)

src/main.jsを起点として、public/bundle.jsを生成する

```js
import svelte from 'rollup-plugin-svelte';
import resolve from '@rollup/plugin-node-resolve';

export default {
  input: 'src/main.js',
  output: {
    file: 'public/bundle.js',
    format: 'iife'
  },
  plugins: [
    svelte({
      include: 'src/**/*.svelte',
      emitCss: false,
    }),
    resolve({ browser: true }),
  ]
}
```

*src/main.js*

```js
import App from './App.svelte';

const app = new App({
	target: document.body,
	props: {
		name: 'world'
	}
});

export default app;
```

*src/App.svelte*


```svelte
<script>
	export let name;
</script>

<main>
	<h1>Hello {name}!</h1>
</main>

<style>
	h1 {
		color: #ff3e00;
	}
</style>
```


コンパイル

./public/bundle.js が生成される

```bash
rollup -c
```


*index.html*

ビルドしたjsを読み込んで実行

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script defer src="./public/bundle.js"></script>
</head>
<body>
</body>
</html>
```
