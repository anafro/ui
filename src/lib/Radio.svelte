<script lang="ts">
    interface RadioProps {
        name: string;
        value: string;
        group: string;
    }
    
    let {
        name,
        value,
        group = $bindable(),
    }: RadioProps = $props();
</script>

<input type="radio" {name} {value} bind:group>

<style lang="sass">
    input
        width: 1rem
        aspect-ratio: 1
</style>