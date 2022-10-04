<script lang="ts">
	import Bmi from '$lib/calculators/Bmi.svelte';
	import Whr from '$lib/calculators/Whr.svelte';
	import Whtr from '$lib/calculators/Whtr.svelte';
	import { fade } from 'svelte/transition';
	import { answers } from '$lib/stores';
	import Test from './Test.svelte';
	import Data from './Data.svelte';
	export let weight: number;
	export let height: number;
	export let taille: number;
	export let hip: number;
	export let gender: string;
	export let test: string;
	export let age: number;
</script>

<Test bind:test />

<Data bind:weight bind:height bind:taille bind:hip bind:gender bind:age />

{#if test != ''}
	{#if taille != '' || (height != '' && age == '')}
		<h2>Ihr Resultat</h2>

		{#if $answers.risk1_6.includes('bmi')}
			<div in:fade={{ duration: 3000 }}>
				<Bmi
					bind:weight={$answers.risk1_1}
					bind:height={$answers.risk1_2}
					bind:gender={$answers.risk1_5}
				/>
			</div>
		{/if}
		{#if $answers.risk1_6.includes('whr')}
			<div in:fade={{ duration: 3000 }}>
				<Whr
					bind:taille={$answers.risk1_3}
					bind:hip={$answers.risk1_4}
					bind:gender={$answers.risk1_5}
				/>
			</div>
		{/if}
		{#if $answers.risk1_6.includes('whtr')}
			<div in:fade={{ duration: 3000 }}>
				<Whtr
					bind:height={$answers.risk1_2}
					bind:taille={$answers.risk1_3}
					bind:age={$answers.risk1_7}
				/>
			</div>
		{/if}

		<h4>Hinweis:</h4>
		<p>
			Eine endgültige Diagnose jeglicher Art kann nur <br />
			mit einer Untersuchung durch einen Arzt gemacht werden.
		</p>
	{/if}
{/if}
