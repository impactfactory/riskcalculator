<script lang="ts">
	//import { answers } from '$lib/stores';
	import { fade } from 'svelte/transition';
	import Bel from './calculators/Bel.svelte';
	import Bmidge from './calculators/Bmidge.svelte';
	import Bminrc from './calculators/Bminrc.svelte';
	import Bmiwho from './calculators/Bmiwho.svelte';
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
	<h2>Ihr Resultat</h2>

	{#if test.includes('bmiwho')}
		<div in:fade={{ duration: 3000 }}>
			<Bmiwho bind:weight bind:height />
		</div>
	{/if}
	{#if test.includes('bmidge')}
		<div in:fade={{ duration: 3000 }}>
			<Bmidge bind:weight bind:height bind:gender />
		</div>
	{/if}
	{#if test.includes('bminrc')}
		<div in:fade={{ duration: 3000 }}>
			<Bminrc bind:weight bind:height bind:age />
		</div>
	{/if}
	{#if test.includes('whr')}
		<div in:fade={{ duration: 3000 }}>
			<Whr bind:taille bind:hip bind:gender />
		</div>
	{/if}
	{#if test.includes('whtr')}
		<div in:fade={{ duration: 3000 }}>
			<Whtr bind:height bind:taille bind:age />
		</div>
	{/if}
	{#if test.includes('bel')}
		<div in:fade={{ duration: 3000 }}>
			<Bel bind:taille bind:gender />
		</div>
	{/if}

	<p>
		<strong>Wichtiger Hinweis:</strong> <br />
		Eine endgültige Diagnose jeglicher Art kann nur mit einer Untersuchung durch einen Arzt gemacht werden.
	</p>
{/if}

{test} and {gender} and {height}
from results<br />

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
