<script lang="ts">
    import type {Snippet} from "svelte";
    
    interface LogotypeProps {
        children: Snippet;
        name: string;
    }
    
    const {
        children,
        name,
    }: LogotypeProps = $props();
</script>

<div id="logotype">
    {@render children?.()}
    <div id="logotype__title">
        <span id="logotype__ecosystem-name">Anatoly Frolov: </span>
        <h1 id="logotype__tool-name">{name}</h1>
    </div>
</div>

<style lang="sass">
    #logotype
        display: flex
        align-items: center
        column-gap: 0.75rem
    
    #logotype__title
        display: flex
        align-items: center
        column-gap: 0.25rem
        
    #logotype__tool-name
        font-size: 1rem
        margin: 0
        font-weight: 1000
</style>
