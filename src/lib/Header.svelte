<script lang="ts">
    import Logotype from "$lib/Logotype.svelte";
    import type {Snippet} from "svelte";
    
    interface HeaderProps {
        name: string;
        logotype: Snippet;
    }
    
    const {
        name,
        logotype,
    }: HeaderProps = $props();
</script>

<header>
    <Logotype {name}>
        {@render logotype?.()}
    </Logotype>
</header>

<style lang="sass">
    @use "../styles/colors"
    @use "../styles/spacings"
    
    header
        background-color: colors.$dark-surface
        padding-block: 0.75rem
        padding-inline: spacings.$inline-space
</style>