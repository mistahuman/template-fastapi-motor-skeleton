<script lang="ts">
	import FooterBar from "$lib/components/generic/FooterBar.svelte";
	import HeaderBar from "$lib/components/generic/HeaderBar.svelte";
</script>

<div class="grid h-screen grid-rows-[auto_1fr_auto] max-w-full">
    <HeaderBar />
    <!-- Grid Column -->
    <!-- Main -->
    <main class="bg-surface-50-950 space-y-4 p-4">
        <slot></slot>
    </main>
    <!-- Footer -->
    <FooterBar />
</div>