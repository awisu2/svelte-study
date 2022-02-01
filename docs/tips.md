# tips

- Objectの展開をすることでDomの各要素へ反映される(サンプルを後述)
  - キーと元から記載していた要素がぶつかっても上書きはされない
- カスタムコンポーネントにはOjbectで値を渡すと予約語であるclassなどが渡しやすい(typescript推奨)

## Objectの展開をすることでDomの各要素へ反映される

```ts
<script lang="ts">
  type Setting ={
    class?: string,
    style?: string
  }

  export let wrapper: Setting = {}
  export let inner: Setting = {}
</script>

<div class="scroller" {...wrapper}>
  <div {...inner}>
    <slot />
  </div>
</div>
```
