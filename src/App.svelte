<script>
    import "./app.css";
    import { Badge, Img, Heading, A, P, Span, Secondary, Hr, AccordionItem, Accordion } from "flowbite-svelte";
    import { GithubSolid, LinkedinSolid, FileCodeSolid, SeedlingSolid, UserCircleSolid } from "flowbite-svelte-icons";
    import Project from "./components/Project.svelte";
    import CertificationList from "./components/CertificationList.svelte";

    const stacks = ["Python", "PHP", "Typescript", "React", "Svelte", "Docker", "SQL", "Qt", "Rust", "Tailwind", "Bootstrap", "Shadcn", "Flowbite", "Next.js"];

    const projects = [
        {
            image: "https://github.com/user-attachments/assets/4fa4f56a-6afc-434b-8478-4b750199f6d6",
            name: "QExtraWidgets",
            description: "Uma biblioteca abrangente de widgets modernos, responsivos e ricos em recursos para aplicações PySide6. Inclui componentes de alto nível como tabelas filtráveis estilo Excel, seletores de emoji, menus em acordeão e ícones sensíveis ao tema.",
            stacks: ["Python", "Qt"],
            github: "https://github.com/gpedrosobernardes/QExtraWidgets",
        },
        {
            image: "https://raw.githubusercontent.com/gpedrosobernardes/discord_bot_creator/refs/heads/master/assets/icons/icon.svg",
            name: "Discord Bot Creator",
            description: "Um software open source desenvolvido em Python, utilizando a Discord API e PySide6, projetado para facilitar a criação e o desenvolvimento de bots personalizados para o Discord.",
            stacks: ["Python", "Qt"],
            github: "https://github.com/gpedrosobernardes/discord_bot_creator"
        }
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

    const certificationCount = certifications.length;
</script>

<main class="flex flex-col items-center gap-20 p-10 sm:p-20 bg-radial-[at_25%_25%] from-primary-950 to-black to-75% min-h-screen">
    <section class="w-full sm:w-4/6">
        <div class="flex items-center gap-3">
            <UserCircleSolid class="shrink-0 inline h-8 w-8 text-primary-400" />
            <Heading tag="h2" class="inter-font">Sobre mim</Heading>
        </div>
        <Hr/>
        <div class="flex flex-wrap justify-center gap-10">
            <Img
                src="src/assets/photo.png"
                alt="A photo of myself"
                class="h-64 w-64 sm:h-96 sm:w-96 rounded-full"
            />
            <div class="flex flex-col justify-between min-w-xs max-w-xl gap-3">
                <div class="flex flex-col min-h-64 gap-3">
                    <div>
                        <Heading tag="h3">Gustavo Pedroso Bernardes</Heading>
                        <Heading tag="h4"><Secondary>Desenvolvedor Fullstack</Secondary></Heading>
                    </div>
                    <P>
                        Atuo como analista de suporte há cerca de 2 anos na Concentrix. Atualmente estou focado no meu desenvolvimento como programador, buscando aprender novos conceitos e fortalecer os já existentes.
                    </P>
                    <div class="flex flex-wrap gap-1">
                        {#each stacks as stack}
                            <Badge rounded>{stack}</Badge>
                        {/each}
                    </div>
                </div>
                <div>
                    <A
                        href="https://github.com/gpedrosobernardes"
                        color="primary"
                        class="font-medium hover:underline"
                    >
                        <GithubSolid class="shrink-0 h-5 w-5 mr-1"/>
                        Github
                    </A>
                    <A
                        href="https://www.linkedin.com/in/gustavo-pedroso-bernardes-a928b51a4/"
                        color="primary"
                        class="font-medium hover:underline"
                    >
                        <LinkedinSolid class="shrink-0 h-5 w-5 mr-1"/>
                        LinkedIn
                    </A>
                </div>
            </div>
        </div>
    </section>
    <section class="w-full sm:w-4/6">
        <div class="flex items-center gap-3">
            <FileCodeSolid class="shrink-0 inline h-8 w-8 text-primary-400" />
            <Heading tag="h2" class="inter-font">Projetos</Heading>
        </div>
        <Hr/>
        <div class="flex flex-wrap justify-center gap-10">
            {#each projects as project}
                <Project {...project}></Project>
            {/each}
        </div>
    </section>
    <section class="w-full sm:w-4/6">
        <div class="flex items-center gap-3">
            <SeedlingSolid class="shrink-0 inline h-8 w-8 text-primary-400" />
            <Heading tag="h2" class="inter-font">Certificados <Secondary>({certificationCount})</Secondary></Heading>
        </div>
        <Hr/>
        <CertificationList certifications={visibleCertifications}/>
        <Accordion flush>
          <AccordionItem>
                {#snippet header()}Mostrar todos{/snippet}
                <CertificationList certifications={certificationsRest}/>
          </AccordionItem>
        </Accordion>
    </section>
</main>
