<script>
    import Certification from "./Certification.svelte";

    let { certifications } = $props();
</script>

<div>
    {#each certifications as certification}
        <Certification {...certification}></Certification>
    {/each}
</div>
