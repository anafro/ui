<script lang="ts">
    import type {Snippet} from "svelte";
    import Header from "$lib/Header.svelte";
    
    interface ToolProps {
        children: Snippet;
        logotype: Snippet;
        name: string;
    }
    
    const {
        children,
        logotype,
        name,
    }: ToolProps = $props();
</script>

<div id="tool">
    <Header
        {name}
        {logotype}
    ></Header>
    
    <div id="tool__body">
        {@render children?.()}
    </div>
</div>

<style lang="sass">
    @use '../styles/colors'
    @use '../styles/spacings'
    @import url('https://fonts.googleapis.com/css2?family=Anonymous+Pro:ital,wght@0,400;0,700;1,400;1,700&family=Overpass:ital,wght@0,100..900;1,100..900&display=swap')
    
    @property --accent-color
        syntax: "<color>"
        inherits: true
        initial-value: colors.$dark-blue
        
    :global(html)
        font-size: 100%
    
    :global(body)
        background-color: colors.$dark-background
        margin: 0
        padding: 0
        box-sizing: border-box
    
    *
        color: colors.$dark-foreground
        font-family: 'Overpass', sans-serif
        accent-color: var(--accent-color)
    
    :global(*)::selection
        background: color-mix(in srgb, transparent, var(--accent-color) 15%)
        
    #tool__body
        max-width: 100vw
        padding-inline: spacings.$inline-space
        padding-block: spacings.$block-space
</style>