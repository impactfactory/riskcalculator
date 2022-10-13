<script lang="ts">
	import Exit from '$lib/Exit.svelte';
	import Calc from '$lib/inputs/Calc.svelte';
	import { answers } from '$lib/stores';
	import { fade } from 'svelte/transition';

	let ExitButton = false;

	let age: number;
	let gender: string;
	let height: number;
	let hip: number;
	let taille: number;
	let test: any;
	let weight: number;
</script>

<div in:fade={{ duration: 1000 }}>
	<Calc
		bind:age={$answers.risk1_7}
		bind:weight={$answers.risk1_1}
		bind:height={$answers.risk1_2}
		bind:taille={$answers.risk1_3}
		bind:hip={$answers.risk1_4}
		bind:gender={$answers.risk1_5}
		bind:test={$answers.risk1_6}
	/>
</div>

<style>
	div {
		display: block;
		width: 380px;
	}
</style>
