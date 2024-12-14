<script lang="ts">
    interface FieldProps {
        value: string;
        placeholder: string;
        disabled?: boolean;
    }
    
    let {
        value = $bindable(),
        placeholder,
        disabled = false,
    }: FieldProps = $props();
</script>

<input type="text" bind:value {placeholder} {disabled}>

<style lang="sass">
    @use "../styles/colors"
    @use "../styles/border-radiuses"
    
    input
        all: unset
        background-color: colors.$dark-component
        border-radius: border-radiuses.$small-border-radius
        color: colors.$dark-foreground
        padding-block: 0.25rem
        padding-inline: 0.5rem
        min-width: 8rem
        
    input:not(:disabled):focus
        outline: 1px solid color-mix(in srgb, transparent, var(--accent-color) 50%)
        
    input::placeholder
        color: transparentize(colors.$dark-foreground, 0.80)
        
    input:disabled
        background-color: colors.$dark-disabled-background
        color: colors.$dark-disabled-foreground
        
</style>