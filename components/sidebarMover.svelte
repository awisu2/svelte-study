<script lang="ts">
    import { onMount } from 'svelte';

    let bar: HTMLElement
    let width = 200;

    onMount(() => {
        setSideMover(bar)
    })

    function setSideMover(mover: HTMLElement) {
        let mouseDown = false
        let halfWidth = 0
        let resetMouseDownId: NodeJS.Timeout = null

        // use the center. because If use a halfway position, the mouse will leave immediately
        const rect = mover.getBoundingClientRect()
        halfWidth = rect.width / 2

        mover.onmousedown = () => {
            // clear selection because not run onmousemove event if any selection exeists
            const selection = getSelection()
            if (selection) {
                selection.empty()
            }
            mouseDown = true
        }

        mover.onmouseup = () => mouseDown = false
        mover.onmouseleave = () => {
            if (!mouseDown) return
            resetMouseDownId = setTimeout(() => {
                mouseDown = false
            }, 300)
        }
        mover.onmouseenter = () => {
            if (resetMouseDownId) {
            clearTimeout(resetMouseDownId)
            }
        }

        // update sidebar width
        // INFO: use parent element event. because can run event wide area.
        let el = mover.parentElement
        if (!el.onmousemove) {
            el = mover
        }
        el.parentElement.onmousemove = (ev: MouseEvent)  => {
        if (!mouseDown) {
            return
        }

        // !! modify it for your code
        const _width = ev.clientX - halfWidth
            if (width != _width) width = _width
        }
    }
</script>

<article class="layout grid h-full">
    <div style="{`grid-area: side; width: ${width}px;`}">
        side
    </div>
    <div bind:this="{bar}" class="cursor-col-resize bg-gray-400 relative w-2" style="grid-area: bar;">
    </div>
    <div style="grid-area: main;" class="h-full max-h-full">
        main content
    </div>
  </article>
  
<style>
    .layout {
        grid-template:
            "side bar main" 1fr
            / auto auto 1fr;
    }
</style>
