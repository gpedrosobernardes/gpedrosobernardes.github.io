<script>
	import { Badge, Heading, P, A, Secondary, Hr } from 'flowbite-svelte';
	import { GithubSolid } from "flowbite-svelte-icons";
	let { image, name, description, stacks, github } = $props();
</script>

<div class="flex flex-col justify-between h-64 max-w-xl">
    <div class="flex flex-col gap-3">
        <Heading tag="h3">{name}</Heading>
        <P>{description}</P>
        <div class="flex flex-wrap gap-1">
            {#each stacks as stack}
                <Badge rounded>{stack}</Badge>
            {/each}
        </div>
    </div>
    <A
        href={github}
        color="primary"
        class="font-medium hover:underline"
    >
        <GithubSolid class="shrink-0 h-5 w-5 mr-1"/>
        Github
    </A>
</div>
