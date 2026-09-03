<script>
    import "./app.css";
    import {
        Img,
        Heading,
        A,
        P,
        Secondary,
        AccordionItem,
        Accordion,
    } from "flowbite-svelte";
    import {
        GithubSolid,
        LinkedinSolid,
        FileCodeSolid,
        SeedlingSolid,
        UserCircleSolid,
    } from "flowbite-svelte-icons";
    import Project from "./components/Project.svelte";
    import CertificationList from "./components/CertificationList.svelte";
    import VL from "./components/VL.svelte";
    import Stacks from "./components/Stacks.svelte";
    import Section from "./components/Section.svelte";

    const stacks = [
        "Python",
        "PHP",
        "Typescript",
        "React",
        "Svelte",
        "Docker",
        "SQL",
        "Qt",
        "Rust",
        "Tailwind",
        "Bootstrap",
        "Shadcn",
        "Flowbite",
        "Next.js",
    ];

    const projects = [
        {
            name: "QExtraWidgets",
            description:
                "Uma biblioteca abrangente de widgets modernos, responsivos e ricos em recursos para aplicações PySide6. Inclui componentes de alto nível como tabelas filtráveis estilo Excel, seletores de emoji, menus em acordeão e ícones sensíveis ao tema.",
            stacks: ["Python", "Qt"],
            github: "https://github.com/gpedrosobernardes/QExtraWidgets",
        },
        {
            name: "Discord Bot Creator",
            description:
                "Um software open source desenvolvido em Python, utilizando a Discord API e PySide6, projetado para facilitar a criação e o desenvolvimento de bots personalizados para o Discord.",
            stacks: ["Python", "Qt"],
            github: "https://github.com/gpedrosobernardes/discord_bot_creator",
        },
    ];

    const certifications = [
        {
            name: "Lógica de programação essencial",
            platform: "DIO",
            date: "mar de 2020",
        },
        {
            name: "Introdução à programação com Python",
            platform: "DIO",
            date: "abr de 2020",
        },
        {
            name: "Introdução ao Git e Controle de Versões",
            platform: "DIO",
            date: "jul de 2020",
        },
        {
            name: "Primeiros passos com .NET + C#",
            platform: "DIO",
            date: "mai de 2021",
        },
        {
            name: "Começando com o Cisco Packet Tracer",
            platform: "Cisco Networking Academy",
            date: "fev de 2026",
        },
        {
            name: "Conceitos Básicos de Redes",
            platform: "Cisco Networking Academy",
            date: "mar de 2026",
        },
        {
            name: "Fundamentos de Docker",
            platform: "LinkedIn Learning",
            date: "jun de 2026",
        },
        {
            name: "Fundamentos de TypeScript",
            platform: "LinkedIn Learning",
            date: "jun de 2026",
        },
        {
            name: "Fundamentos de React",
            platform: "LinkedIn Learning",
            date: "jul de 2026",
        },
        {
            name: "Fundamentos de Windows para Desenvolvedores",
            platform: "LinkedIn Learning",
            date: "jul de 2026",
        },
        {
            name: "Descubra o CSS",
            platform: "LinkedIn Learning",
            date: "jul de 2026",
        },
        {
            name: "Fundamentos de Rust",
            platform: "LinkedIn Learning",
            date: "jul de 2026",
        },
        {
            name: "Fundamentos de Programação: APIs e Serviços da Web",
            platform: "LinkedIn Learning",
            date: "jul de 2026",
        },
    ].reverse();

    const visibleCertifications = certifications.slice(0, 3);
    const certificationsRest = certifications.slice(3);
</script>

<main class="mx-auto w-5/6 sm:w-4/6">
    <Section title="Sobre mim" icon={UserCircleSolid}>
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-10">
            <Img
                src="/photo.webp"
                alt="A photo of myself"
                class="h-64 w-64 sm:h-80 sm:w-80 rounded-full m-auto "
            />
            <div
                class="max-w-xl m-auto"
            >
                <div>
                    <Heading tag="h3">Gustavo Pedroso Bernardes</Heading>
                    <Heading tag="h4" class="mb-4"
                        ><Secondary>Desenvolvedor Fullstack</Secondary></Heading
                    >
                    <P class="mb-2">
                        Atuo como analista de suporte há cerca de 2 anos na
                        Concentrix. Atualmente estou focado no meu
                        desenvolvimento como programador, buscando aprender
                        novos conceitos e fortalecer os já existentes.
                    </P>
                    <Stacks {stacks}></Stacks>
                </div>
                <div class="flex items-center gap-2 mt-10">
                    <A
                        href="https://github.com/gpedrosobernardes"
                        color="primary"
                        class="font-medium hover:underline"
                    >
                        <GithubSolid class="shrink-0 h-6 w-6 mr-2" />
                        Github
                    </A>
                    <VL></VL>
                    <A
                        href="https://www.linkedin.com/in/gustavo-pedroso-bernardes-a928b51a4/"
                        color="primary"
                        class="font-medium hover:underline"
                    >
                        <LinkedinSolid class="shrink-0 h-6 w-6 mr-2" />
                        LinkedIn
                    </A>
                </div>
            </div>
        </div>
    </Section>
    <Section title="Projetos" icon={FileCodeSolid}>
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-10">
            {#each projects as project}
                <Project {...project}></Project>
            {/each}
        </div>
    </Section>
    <Section title="Certificados" icon={SeedlingSolid}>
        <CertificationList certifications={visibleCertifications} />
        <Accordion flush>
            <AccordionItem>
                {#snippet header()}Mostrar todos{/snippet}
                <CertificationList certifications={certificationsRest} />
            </AccordionItem>
        </Accordion>
    </Section>
</main>
