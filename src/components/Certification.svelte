<script lang="ts">
	import { Img, Heading, P, Secondary } from 'flowbite-svelte';

    const platformToImage = {
        "LinkedIn Learning": "/linkedin.webp",
        "Cisco Networking Academy": "/cisco.webp",
        "DIO": "/dio.webp"
    }

	let { name, platform, date }: { name: string; platform: keyof typeof platformToImage; date: string } = $props();

	const image = platformToImage[platform];
</script>

<div class="flex gap-6 max-w-2xl mb-6">
    <Img class="rounded-lg w-15 h-15 sm:w-20 sm:h-20" src={image}></Img>
    <div>
        <Heading tag="h5">{name}</Heading>
        <Heading tag="h5" class="mb-4"><Secondary>{platform}</Secondary></Heading>
        <P>Emitido em: {date}</P>
    </div>
</div>
