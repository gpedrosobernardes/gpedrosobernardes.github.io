<script>
	import { Img, Heading, P, A, Secondary, Hr } from 'flowbite-svelte';

	let { name, platform, date } = $props();

	const platformToImage = {
	    "LinkedIn Learning": "/linkedin.webp",
		"Cisco Networking Academy": "/cisco.webp",
		"DIO": "/dio.webp"
	}

	const image = platformToImage[platform];
</script>

<div class="flex gap-6 max-w-2xl">
    <Img class="rounded-lg w-15 h-15 sm:w-20 sm:h-20" src={image}></Img>
    <div class="flex flex-col justify-between">
        <div>
            <Heading tag="h5">{name}</Heading>
            <Heading tag="h5"><Secondary>{platform}</Secondary></Heading>
        </div>
        <P>Emitido em: {date}</P>
    </div>
</div>
