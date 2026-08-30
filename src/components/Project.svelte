<script>
	import { Badge, Heading, P, A } from 'flowbite-svelte';
	import { GithubSolid } from "flowbite-svelte-icons";
	import Stacks from './Stacks.svelte';
	let { name, description, stacks, github } = $props();
</script>

<div class="max-w-xl mx-auto">
    <Heading tag="h3" class="mb-4">{name}</Heading>
    <P class="mb-2">{description}</P>
    <Stacks stacks={stacks}></Stacks>
    <A
        href={github}
        color="primary"
        class="font-medium hover:underline mt-10"
    >
        <GithubSolid class="shrink-0 h-6 w-6 mr-2"/>
        Github
    </A>
</div>
