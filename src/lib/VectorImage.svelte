<script lang="ts">
    import type {Snippet} from "svelte";
    
    interface VectorImageProps {
        children: Snippet;
        viewBox: string;
    }
    
    const {
        children,
        viewBox,
    }: VectorImageProps = $props();
</script>

<svg class="vector-image" {viewBox}>
    {@render children?.()}
</svg>

<style lang="sass">
    .vector-image
        max-width: 1rem
</style>