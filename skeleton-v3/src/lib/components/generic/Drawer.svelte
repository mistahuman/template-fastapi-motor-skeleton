<script lang="ts">
    import { Menu, X } from "@lucide/svelte";

    export let navigation: { href: string; label: string; target: string }[] =
        [];
    export let base =
        "xl:hidden preset-filled-surface-100-900 shadow-xl fixed top-0 left-0 bottom-0 h-screen z-50 w-[320px] p-4 pb-24 space-y-10 overflow-y-auto transition-transform duration-100 -translate-x-[320px]";
    export let classes = "";

    let drawerOpen = false;

    function toggleDrawer() {
        drawerOpen = !drawerOpen;
    }
</script>

<!-- Drawer -->
<div
    class={`${base} ${classes} ${drawerOpen ? "!translate-x-0" : ""}`}
    id="drawer"
>
    <!-- Header -->
    <header class="flex justify-between items-center">
        <h2 class="h3">Template Skeleton</h2>
        <button class="btn-icon" on:click={toggleDrawer}>
            <X size={20} />
        </button>
    </header>

    <!-- Navigation -->
    <nav class="flex flex-col gap-2">
        {#each navigation as link}
            <a
                class="anchor hover:underline"
                href={link.href}
                target={link.target}
                on:click={() => (drawerOpen = false)}
            >
                {link.label}
            </a>
        {/each}
    </nav>

    <!-- Slot -->
    <slot />
</div>

<!-- Hamburger Menu -->
<button class="xl:hidden btn-icon" on:click={toggleDrawer}>
    <Menu size={20} />
</button>
