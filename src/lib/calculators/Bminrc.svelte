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
	export let age: number;
</script>

{#if isFinite((weight / (height * height)) * 10000) && weight && height && age}
	{@const bmi = (weight / (height * height)) * 10000}
	<div in:fade={{ duration: 3000 }}>
		<h3 class="pb-0 mb-0">
			BMI: {bmi.toFixed(1)} /

			<!-- < 35  -->
			{#if age < 35}
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
				<!-- 35-44 -->
			{:else if age >= 35 && age <= 44}
				{#if bmi < 16}
					<Under3 />
				{:else if bmi >= 16 && bmi <= 16.9}
					<Under2 />
				{:else if bmi >= 17 && bmi <= 18.49}
					<Under1 />
				{:else if bmi >= 18.5 && bmi <= 25.9}
					<Norm />
				{:else if bmi >= 26 && bmi <= 30.9}
					<Over />
				{:else if bmi >= 31 && bmi <= 35.9}
					<Adi1 />
				{:else if bmi >= 36 && bmi <= 40.9}
					<Adi2 />
				{:else if bmi >= 41}
					<Adi3 />
				{/if}
				<!-- 45 - 54 -->
			{:else if age >= 45 && age <= 54}
				{#if bmi < 16}
					<Under3 />
				{:else if bmi >= 16 && bmi <= 16.9}
					<Under2 />
				{:else if bmi >= 17 && bmi <= 18.49}
					<Under1 />
				{:else if bmi >= 18.5 && bmi <= 26.9}
					<Norm />
				{:else if bmi >= 27 && bmi <= 31.9}
					<Over />
				{:else if bmi >= 32 && bmi <= 36.9}
					<Adi1 />
				{:else if bmi >= 37 && bmi <= 41.9}
					<Adi2 />
				{:else if bmi >= 42}
					<Adi3 />
				{/if}
				<!-- 55-65 -->
			{:else if age >= 55 && age <= 65}
				{#if bmi < 16}
					<Under3 />
				{:else if bmi >= 16 && bmi <= 16.9}
					<Under2 />
				{:else if bmi >= 17 && bmi <= 18.49}
					<Under1 />
				{:else if bmi >= 18.5 && bmi <= 27.9}
					<Norm />
				{:else if bmi >= 28 && bmi <= 32.9}
					<Over />
				{:else if bmi >= 33 && bmi <= 37.9}
					<Adi1 />
				{:else if bmi >= 38 && bmi <= 42.9}
					<Adi2 />
				{:else if bmi >= 43}
					<Adi3 />
				{/if}
				<!-- 65+ -->
			{:else if age > 65}
				{#if bmi < 16}
					<Under3 />
				{:else if bmi >= 16 && bmi <= 16.9}
					<Under2 />
				{:else if bmi >= 17 && bmi <= 18.49}
					<Under1 />
				{:else if bmi >= 18.5 && bmi <= 28.9}
					<Norm />
				{:else if bmi >= 29 && bmi <= 33.9}
					<Over />
				{:else if bmi >= 34 && bmi <= 38.9}
					<Adi1 />
				{:else if bmi >= 39 && bmi <= 43.9}
					<Adi2 />
				{:else if bmi >= 44}
					<Adi3 />
				{/if}
			{/if}
		</h3>
		<small>* Body Mass Index / Gewicht durch Grösse im Quadrat, Berechnungsmethodik NRC</small>
	</div>
{/if}
