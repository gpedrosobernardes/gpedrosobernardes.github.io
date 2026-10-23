<script lang="ts">
    import { type Component, type Snippet } from "svelte";
    interface Props {
        children: Snippet;
        title: string;
        icon: Component;
    }
    const { children, title, icon }: Props = $props();

    import { Heading, Hr } from "flowbite-svelte";
    import { IconSolid } from "flowbite-svelte-icons";

    const config: {
        size: "md" | "xs" | "sm" | "lg" | "xl" | undefined;
    } = {
        size: "xl",
    };
</script>

<section class="my-10">
    <div class="flex items-center gap-4">
        <IconSolid {...config} Icon={icon} class="text-primary-400"/>
        <Heading tag="h2" class="inter-font">{title}</Heading>
    </div>
    <Hr />
    {@render children()}
</section>
