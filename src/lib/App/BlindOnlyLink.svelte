<script lang="ts">
    export let href: string
    export let id: string = null
</script>

<a {href} {id} class="blind-only-link" tabindex="0">
    <slot />
</a>

<style>
    .blind-only-link {
        position: absolute;
        background: var(--h-color-mode);
        outline: solid 0.1em var(--h-color-master);
        z-index: 999999999999;
    }

    .blind-only-link {
        pointer-events: none;
        opacity: 0;
    }

    .blind-only-link:focus,
    .blind-only-link:focus-within {
        pointer-events: unset;
        opacity: unset;
    }
</style>
