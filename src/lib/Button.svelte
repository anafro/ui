<script lang="ts">
    import type {Snippet} from "svelte";
    
    interface ButtonProps {
        children: Snippet;
        primary?: boolean;
        disabled?: boolean;
    }
    
    let {
        children,
        primary = false,
        disabled = false,
    }: ButtonProps = $props();
</script>

<button class:primary {disabled}>
    {@render children?.()}
</button>

<style lang="sass">
    @use "../styles/colors"
    @use "../styles/border-radiuses"
    @use "../styles/transitions"
    @use "../styles/easings"
    @use "../styles/transforms"
    
    button
        all: unset
        cursor: pointer
        min-width: 2.5rem
        text-align: center
        padding-inline: 0.5rem
        padding-block: 0.25rem
        border-radius: border-radiuses.$small-border-radius
        font-weight: 600
        @include transitions.fast-transition
        
        &.primary
            color: colors.$dark-surface
            background: var(--accent-color)
            
        &:not(.primary)
            color: colors.$dark-foreground
            background: colors.$dark-component
            
        
    button:not(:disabled):hover
        &.primary
            background: color-mix(in srgb, white, var(--accent-color) 90%)
            outline: 0.25rem solid color-mix(in srgb, transparent, var(--accent-color) 20%)
            filter: drop-shadow(0 0 0.5rem color-mix(in srgb, transparent, var(--accent-color) 40%))
            
        &:not(.primary)
            background: color-mix(in srgb, white, colors.$dark-component 98%)
            filter: drop-shadow(0 0 0.5rem color-mix(in srgb, transparent, colors.$dark-component 40%))
        
    button:not(:disabled):active
        outline: 0rem
        scale: transforms.$active-scale
        
    button:disabled
        color: colors.$dark-disabled-foreground
        background: colors.$dark-disabled-background
        cursor: not-allowed
        
</style>