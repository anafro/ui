<script lang="ts">
    
    interface CheckboxProps {
        value: string;
        label: string;
        group: string[];
    }
    
    let {
        value,
        label,
        group = $bindable(),
    }: CheckboxProps = $props();
    
    const id = $state(crypto.randomUUID());
    
    function toggleValueInGroup(): void {
        if (group.includes(value)) {
            group = group.filter(v => v !== value);
        } else {
            group = [value, ...group];
        }
    }
</script>

<div class="checkbox">
    <input {id} type="checkbox" onchange={toggleValueInGroup} {value}>
    <label for={id}>{label}</label>
</div>

<style lang="sass">
    input
        width: 1rem
        aspect-ratio: 1
</style>