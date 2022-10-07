<script lang="ts">
	import { fade } from 'svelte/transition';
	import Adi1 from './messages/Adi1.svelte';
	import Adi2 from './messages/Adi2.svelte';
	import Adi3 from './messages/Adi3.svelte';
	import Norm from './messages/Norm.svelte';
	import Over from './messages/Over.svelte';
	import Under from './messages/Under.svelte';

	export let weight: number;
	export let height: number;
	export let gender: string;
</script>

{#if !isNaN((weight / (height * height)) * 10000) && gender && weight && height}
	{@const bmi = (weight / (height * height)) * 10000}
	<div in:fade={{ duration: 3000 }}>
		<h3 class="pb-0 mb-0">
			BMI: {bmi.toFixed(1)} /
			{#if gender == 'weiblich'}
				{#if bmi < 19}
					<Under />
				{:else if bmi >= 19 && bmi <= 23.9}
					<Norm />
				{:else if bmi >= 24 && bmi <= 29.99}
					<Over />
				{:else if bmi >= 30 && bmi <= 34.99}
					<Adi1 />
				{:else if bmi >= 35 && bmi <= 39.99}
					<Adi2 />
				{:else if bmi >= 40}
					<Adi3 />
				{/if}
			{:else if gender == 'männlich'}
				{#if bmi < 20}
					<Under />
				{:else if bmi >= 20 && bmi <= 24.99}
					<Norm />
				{:else if bmi >= 25 && bmi <= 29.99}
					<Over />
				{:else if bmi >= 30 && bmi <= 34.99}
					<Adi1 />
				{:else if bmi >= 35 && bmi <= 39.99}
					<Adi2 />
				{:else if bmi >= 40}
					<Adi3 />
				{/if}
			{/if}
		</h3>
		<small>* Body Mass Index / Gewicht durch Grösse im Quadrat, Berechnungsmethodik DGE</small>
	</div>
{/if}
