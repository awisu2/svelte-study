<script lang="ts" context="module">
  /**
   * lazy load image for order
   * 
   * order mean nod load currentposition image. load set order.
   */
  let countId = 0
  export const loadNum = 5 // sametime load num
  let currentId = loadNum

  export function reset() {
    currentId = loadNum
    countId = 0
  }

</script>

<script lang="ts">
  import { onDestroy, onMount } from "svelte";

  export let src: string
  export let alt: string
  export let title: string

  let isLoaded = false
  let id: number = -1

  onMount(() => {
    id = countId
    countId += 1
  })
  onDestroy(() => {
    if (intervalId) {
      clearInterval(intervalId)
      intervalId = null
    }
  })

  // load image
  let intervalId = setInterval(() => {
    if (id != -1 && id > currentId) {
      return
    }
    clearInterval(intervalId)
    intervalId = null

    const _image = new Image()
    _image.src = src

    _image.onload = () => {
      isLoaded = true
      currentId += 1
    }
    _image.onerror = (_) => {
      currentId += 1
    }
  }, 10)
</script>

{#if isLoaded}
  <img src="{src}" alt="{alt}" title="{title}" />
{/if}