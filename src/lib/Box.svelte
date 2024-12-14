<script lang="ts">
    import type {Snippet} from "svelte";
    
    type BoxProps = {
        children?: Snippet;
    } & HTMLDivAttributes;
    
    let {
        children,
        ...rest
    }: BoxProps = $props();
</script>

<div {...rest}>
    {@render children?.()}
</div>