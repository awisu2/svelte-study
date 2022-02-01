# svelte study

nodeのuiフレームワークsvelteの勉強リポジトリ。ここでは実際に使っての勉強をします。svelte自体の勉強については公式サイトにて。

## Todo

- [] [SvelteKit • The fastest way to build Svelte apps](https://kit.svelte.dev/)

## 自分の環境で使う方法

現時点で vite-plugin-svelte, rollup-plugin-svelte, svelte-loader をサポートしているとのこと

[Introduction / Making an app • Svelte Tutorial](https://svelte.jp/tutorial/making-an-app)

### 各種ビルド

- rollup-plugin-svelte: rollupコマンドに対応したビルド方法 ([doc](./rollup-svelte/README.md))

## 公式サイト

- [Introduction / Basics • Svelte Tutorial](https://svelte.dev/tutorial/basics)
- [Docs • Svelte](https://svelte.dev/docs)

## docs

- [tips](./docs/tips.md): 知っておくと便利なこと
- [problems](./docs/problems.md): 時折当たる問題メモ

## contents

- [rollup-svelte](./rollup-svelte) : rollup-plugin-svelteを利用して動作をさせてみました
  - rolluup: node.jsでのビルド環境
- [sveltekit](./sveltekit) : svelteの開発補助パッケージsveltekitを利用して動作をさせてみました。viteによってビルド及び動作
- [with webpack](https://github.com/awisu2/webpack-study/tree/main/svelteWithTypescript): webpack + svelte + typescript
