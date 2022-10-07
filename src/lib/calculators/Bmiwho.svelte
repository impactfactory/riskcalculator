<script lang="ts">
	import { fade } from 'svelte/transition';
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
</script>

{#if !isNaN((weight / (height * height)) * 10000) && weight && height}
	{@const bmi = (weight / (height * height)) * 10000}
	<div in:fade={{ duration: 3000 }}>
		<h3 class="pb-0 mb-0">
			BMI: {bmi.toFixed(1)} /

			{#if bmi < 16}
				<Under3 />
			{:else if bmi >= 16 && bmi <= 16.9}
				<Under2 />
			{:else if bmi >= 17 && bmi <= 18.49}
				<Under1 />
			{:else if bmi >= 18.5 && bmi <= 24.9}
				<Norm />
			{:else if bmi >= 25 && bmi <= 29.9}
				<Over />
			{:else if bmi >= 30 && bmi <= 34.9}
				<Adi1 />
			{:else if bmi >= 35 && bmi <= 39.9}
				<Adi2 />
			{:else if bmi >= 40}
				<Adi3 />
			{/if}
		</h3>
		<small> * Body Mass Index / Gewicht durch Grösse im Quadrat, Berechnungsmethodik: WHO </small>
	</div>{/if}
