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
	let test: string;
	let weight: number;
</script>

<Exit {ExitButton} />
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

	<!--
	<Calc bind:age bind:weight bind:height bind:taille bind:hip bind:gender bind:test />
-->
</div>
