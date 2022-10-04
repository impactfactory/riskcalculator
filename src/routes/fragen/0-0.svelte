<script lang="ts">
	import Exit from '$lib/Exit.svelte';
	import Calc from '$lib/inputs/Calc.svelte';

	import StepsButtons from '$lib/StepsButtons.svelte';
	import { answers } from '$lib/stores';
	import YouAreHere from '$lib/YouAreHere.svelte';
	import { fade } from 'svelte/transition';

	let chapterName: string = 'Risikofaktoren';
	let prevPage: string = '3-2';
	let nextPage: string = 'risks_1';
	let ExitButton = false;

	let test: string;

	let weight: number;
	let height: number;
	let hip: number;
	let gender: string;
	let age: number;
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
</div>

<StepsButtons {prevPage} {nextPage} />
