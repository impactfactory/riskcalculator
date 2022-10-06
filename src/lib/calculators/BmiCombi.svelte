<script lang="ts">
	import Adi1 from './messages/Adi1.svelte';
	import Adi2 from './messages/Adi2.svelte';
	import Adi3 from './messages/Adi3.svelte';
	import Norm from './messages/Norm.svelte';
	import Over from './messages/Over.svelte';
	import Under1 from './messages/Under1.svelte';
	import Under2 from './messages/Under2.svelte';
	import Under3 from './messages/Under3.svelte';

	export let weight: number;
	export let height: number;
	export let age: number;
</script>

{#if !isNaN((weight / (height * height)) * 10000)}
	{@const bmi = ((weight / (height * height)) * 10000).toFixed(2)}

	<h3 class="pb-0 mb-0">
		BMI: {bmi.toFixed(1)} /
		{#if age >= 19 && age <= 24}
		    {#if bmi < 19}
				<Under1 />
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
		{:else if age >= 25 && age <= 34}
		
		{:else if age >= 35 && age <= 44}
		{:else if age >= 45 && age <= 54}
		{:else if age >= 55 && age <= 65}
		{:else if age > 65}
		{/if}


			
		{:else if gender == 'männlich'}
			{#if bmi < 20}
				<Under1 />
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
	<small
		>* Body Mass Index / Gewicht durch Grösse im Quadrat, <a
			href="https://www.agla.ch/de/rechner-und-tools/bmi"
			target="_blank"
			rel="noopener">Quelle Berechnungsmethodik</a
		></small
	>
{/if}

<!-- https://plakos-akademie.de/bmi-rechner/ -->
