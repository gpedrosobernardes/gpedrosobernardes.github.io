<script>
	import { Img, Heading, P, A, Secondary, Hr } from 'flowbite-svelte';
	import { GithubSolid } from "flowbite-svelte-icons";

	let { name, platform, date } = $props();

	const platformToImage = {
	    "LinkedIn Learning": "https://media.licdn.com/dms/image/v2/C560BAQHaVYd13rRz3A/company-logo_100_100/company-logo_100_100/0/1638831590218/linkedin_logo?e=1787184000&v=beta&t=2AK44TbvzhvCakCjRxc21q1e_9Y9jbZshBrgqrjFqXk",
		"Cisco Networking Academy": "https://media.licdn.com/dms/image/v2/D4D0BAQEkiQ8pB1hYow/company-logo_100_100/B4DZcSgOD1HMAU-/0/1748362125886/cisco_networking_academy1_logo?e=1787184000&v=beta&t=5SIhzn11A5ke4fthaF3szQPt3sZf8W_3W-BQCsRhvI8",
		"DIO": "https://media.licdn.com/dms/image/v2/D4D0BAQH1TY3FZloIyA/company-logo_100_100/B4DZxMvm8KJwAU-/0/1770814075164/dio_makethechange_logo?e=1787184000&v=beta&t=lDrZlxpve51Sf7dv26U_YT7HM4UFbQTyp41qEz3UuOs"
	}

	const image = platformToImage[platform];
</script>

<div class="flex gap-5 max-w-2xl">
    <Img class="rounded-lg w-15 h-15 sm:w-20 sm:h-20" src={image}></Img>
    <div class="flex flex-col justify-between">
        <div>
            <Heading tag="h5">{name}</Heading>
            <Heading tag="h5"><Secondary>{platform}</Secondary></Heading>
        </div>
        <P>Emitido em: {date}</P>
    </div>
</div>
