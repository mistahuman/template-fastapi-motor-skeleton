<script>
    import Drawer from "$lib/components/basics/Drawer.svelte";
    import Logo from "$lib/components/basics/Logo.svelte";
    import Lightswitch from "$lib/components/basics/LightSwitch.svelte";
    // Icons
    import { Github } from "@lucide/svelte";

    const coreLinks = [
        { href: "/", label: "Home", target: "_self" },
    ];
</script>

<header
    class="sticky top-0 z-50 border-b-[1px] border-surface-500/20 bg-surface-50/90 dark:bg-surface-950/90 backdrop-blur w-full h-[70px] flex items-center"
>
    <div
        class="container mx-auto grid max-w-screen-2xl grid-cols-[auto_1fr_auto] xl:grid-cols-[1fr_auto_1fr] items-center gap-4 px-4 xl:px-10"
    >
        <!-- Left -->
        <div class="flex items-stretch justify-start gap-4">
            <!-- Mobile Nav Drawer -->
            <Drawer navigation={coreLinks}>
                <!-- <Navigation /> -->
            </Drawer>
            <!-- Logo -->
            <a class="hidden xl:inline-block" href="/" title="Mistahuman">
                <Logo width="32" height="32"></Logo>
            </a>
            <div class="hidden xl:flex items-center">
                <!-- Navigation -->
                {#each coreLinks as link}
                    <a
                        class="btn hover:preset-tonal"
                        href={link.href}
                        target={link.target}
                    >
                        {link.label}
                    </a>
                {/each}
            </div>
        </div>
        <!-- Middle -->
        <div class="flex items-center gap-2"></div>
        <!-- Right -->
        <div class="flex justify-end items-stretch gap-2">
            <!-- Mode and Theme -->
            <Lightswitch />
            <!-- Divider -->
            <span class="border-r border-surface-200-800"></span>
            <!-- Social -->
            <nav class="flex items-center gap-1">
                <a
                    class="btn-icon hover:preset-tonal"
                    href="https://github.com/mistahuman"
                >
                    <Github size={20} />
                </a>
            </nav>
        </div>
    </div>
</header>
