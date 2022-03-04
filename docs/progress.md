# progress sample

- `min-h-min` はプログレス部分を表示するために必須
  - [Min\-Height \- Tailwind CSS](https://tailwindcss.com/docs/min-height)
  - . などの文字で内容を確保しようとすると高さ計算がおかしくなる(なった)

## simple

```js
<script lang="ts">
export let max: number = 0
export let size: number = 0
export let index: number = 0 // 0~

$: width = (() => {
  if ((index + size) > max) {
    return (max - index) / max * 100
  } else {
    return size / max * 100
  }
})()
$: left = index / max * 100
</script>

<div class="h-full w-full p-0.5 border border-gray-500 rounded-full bg-white">
  <div class="h-full min-h-min rounded-full bg-blue-600" style="width: {width}%; margin-left: {left}%;"></div>
</div>
```
