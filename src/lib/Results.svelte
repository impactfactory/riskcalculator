<script lang="ts">
	//import { answers } from '$lib/stores';
	import Bel from './calculators/Bel.svelte';
	import Bmidge from './calculators/Bmidge.svelte';
	import Bminrc from './calculators/Bminrc.svelte';
	import Bmiwho from './calculators/Bmiwho.svelte';
	import Disclaimer from './calculators/messages/Disclaimer.svelte';
	import Whr from './calculators/Whr.svelte';
	import Whtr from './calculators/Whtr.svelte';
	export let weight: number;
	export let height: number;
	export let gender: string;
	export let taille: number;
	export let age: number;
	export let test: any;
	export let hip: number;
</script>

{#if test != ''}
	<h3>Ihr Resultat</h3>

	{#if test.includes('bmiwho')}
		<Bmiwho bind:weight bind:height />
	{/if}
	{#if test.includes('bmidge')}
		<Bmidge bind:weight bind:height bind:gender />
	{/if}
	{#if test.includes('bminrc')}
		<Bminrc bind:weight bind:height bind:age />
	{/if}
	{#if test.includes('whr')}
		<Whr bind:taille bind:hip bind:gender />
	{/if}
	{#if test.includes('whtr')}
		<Whtr bind:height bind:taille bind:age />
	{/if}
	{#if test.includes('bel')}
		<Bel bind:taille bind:gender />
	{/if}
	<Disclaimer />
{/if}

<style>
	:global(.under),
	:global(.normal),
	:global(.over),
	:global(.adi) {
		border-radius: 4px;
		color: white;
		padding: 0.1rem 0.25rem 0.2rem 0.25rem;
	}
	:global(.under) {
		background-color: orange;
	}
	:global(.normal) {
		background: green;
	}
	:global(.over) {
		background: orange;
	}
	:global(.adi) {
		background: red;
	}
</style>
