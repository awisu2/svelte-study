# progress sample

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

<div class="relative h-3 p-0.5 border border-gray-500 rounded-full bg-white">
  <div class="relative h-full w-full">
    <div class="absolute h-full rounded-full bg-blue-600" style="width: {width}%; left: {left}%;">.</div>
  </div>
</div>
```
