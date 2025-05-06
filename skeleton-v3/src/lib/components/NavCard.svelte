<script>
	import IconKit from '$lib/components/basics/IconKit.svelte';
	import SimpleIcon from "$lib/components/basics/SimpleIcon.svelte";

	export let title;
	export let content;
	export let href;
	export let icon;
</script>

<a {href} target="_blank" class="card preset-filled-surface-100-900 border-[1px] border-surface-200-800 card-hover overflow-hidden">
	<header class="card-header h4 p-4">{title}</header>
	<section class="p-1 flex flex-col items-center justify-center">
		<span><IconKit name={icon} /></span>

	</section>
	<section class="p-4">{content}</section>

</a>

<style>
	.card-header {
		font-weight: bold;
		margin-bottom: 10px;
	}
</style>
