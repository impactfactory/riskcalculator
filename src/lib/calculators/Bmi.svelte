<script lang="ts">
	export let weight: number;
	export let height: number;
</script>

{#if !isNaN((weight / (height * height)) * 10000)}
	{@const bmi = (weight / (height * height)) * 10000}
	<h3 class="pb-0 mb-0">
		BMI: {bmi.toFixed(1)} /
		{#if bmi < 16}
			<span class="adi">starkes Untergewicht</span>
		{:else if bmi >= 16 && bmi <= 16.99}
			<span class="under">mässiges Untergewicht</span>
		{:else if bmi >= 17 && bmi <= 18.49}
			<span class="under">leichtes Untergewicht</span>
		{:else if bmi >= 18.5 && bmi <= 24.99}
			<span class="normal">Normalgewicht</span>
		{:else if bmi >= 25 && bmi <= 29.99}
			<span class="over">Übergewicht (Präadipositas)</span>
		{:else if bmi >= 30 && bmi <= 34.99}
			<span class="adi">Adipositas Grad 1</span>
		{:else if bmi >= 35 && bmi <= 39.99}
			<span class="adi">Adipositas Grad 2</span>
		{:else if bmi >= 40}
			<span class="adi">Adipositas Grad 3</span>
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
