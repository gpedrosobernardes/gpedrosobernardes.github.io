<script>
    import Certification from "./Certification.svelte";

    let { certifications } = $props();
</script>

<div class="flex flex-col gap-6">
    {#each certifications as certification}
        <Certification {...certification}></Certification>
    {/each}
</div>
