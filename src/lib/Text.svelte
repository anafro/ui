<script lang="ts">
    import type {Snippet} from "svelte";
    
    type TextProps = {
        children?: Snippet;
    } & HTMLSpanAttributes;
    
    let {
        children,
        ...rest
    }: TextProps = $props();
</script>

<span {...rest}>
    {@render children?.()}
</span>