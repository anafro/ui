<script lang="ts">
    import Tool from "$lib/Tool.svelte";
    import VectorImage from "$lib/VectorImage.svelte";
    import Button from "$lib/Button.svelte";
    import Field from "$lib/Field.svelte";
    import Radio from "$lib/Radio.svelte";
    import Checkbox from "$lib/Checkbox.svelte";
    import Text from "$lib/Text.svelte";
    import Box from "$lib/Box.svelte";
    
    let filename: string = $state('');
    let checked: string[] = $state([]);
    let selected: string = $state('a');
</script>

{#snippet logotype()}
    <VectorImage viewBox="0 0 16.43 12.81">
        <defs>
            <style>
                .cls-1 {
                    fill: var(--accent-color);
                }
            </style>
        </defs>
        <path class="cls-1" d="M2.28.16C2.35.06,2.47,0,2.59,0h2.74s5.33,0,5.33,0h2.16c.32,0,.5.36.31.62l-1.23,1.65c-.07.1-.19.16-.31.16h-2.74s-5.33,0-5.33,0H1.36c-.32,0-.5-.36-.31-.62L2.28.16Z"/>
        <path class="cls-1" d="M4.77,10.53c.07-.1.19-.16.31-.16h2.74s5.33,0,5.33,0h2.16c.32,0,.5.36.31.62l-1.23,1.65c-.07.1-.19.16-.31.16h-2.74s-5.33,0-5.33,0h-2.16c-.32,0-.5-.36-.31-.62l1.23-1.65Z"/>
        <path class="cls-1" d="M14.82,1.59l-1.42,2.02c-.21.3.08.7.44.59l2.32-.74c.25-.08.35-.38.2-.59l-.9-1.28c-.15-.22-.48-.22-.63,0Z"/>
        <path class="cls-1" d="M1.61,11.77l1.42-2.02c.21-.3-.08-.7-.44-.59l-2.32.74c-.25.08-.35.38-.2.59l.9,1.28c.15.22.48.22.63,0Z"/>
    </VectorImage>
{/snippet}

<Tool name="Zipline Archiver" {logotype} --accent-color="#AAD94C">
    <Box id="stack">
        <Button primary>Primary</Button>
        <Button primary disabled>Primary (Disabled)</Button>
        <Button>Secondary</Button>
        <Button disabled>Secondary (Disabled)</Button>
        <Text>The filename you entered is "{filename}".</Text>
        <Field placeholder="File name..." bind:value={filename}></Field>
        <Field placeholder="File name..." value="Hello, world!" disabled></Field>
        <Text>The selected item is "{selected}".</Text>
        <Radio name="radio" value="a" bind:group={selected}></Radio>
        <Radio name="radio" value="b" bind:group={selected}></Radio>
        <Radio name="radio" value="c" bind:group={selected}></Radio>
        <Text>The selected items are "{checked}".</Text>
        <Checkbox value="a" label="Selects an A" bind:group={checked}></Checkbox>
        <Checkbox value="b" label="Selects a B" bind:group={checked}></Checkbox>
        <Checkbox value="c" label="Selects a C" bind:group={checked}></Checkbox>
    </Box>
</Tool>

<style lang="sass">
    :global(#stack)
        display: flex
        flex-direction: column
        align-items: start
        row-gap: 0.5rem
</style>