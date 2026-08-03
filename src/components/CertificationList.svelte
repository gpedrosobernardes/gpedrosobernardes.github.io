<script>
    import Certification from "./Certification.svelte";

    let { certifications } = $props();
</script>

<div class="flex flex-col gap-5">
    {#each certifications as certification}
        <Certification {...certification}></Certification>
    {/each}
</div>
