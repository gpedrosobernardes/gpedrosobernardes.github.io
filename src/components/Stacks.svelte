<script>
    import { Badge } from "flowbite-svelte";

    let { stacks } = $props();
</script>

<div class="flex flex-wrap gap-2">
    {#each stacks as stack}
        <Badge rounded>{stack}</Badge>
    {/each}
</div>
