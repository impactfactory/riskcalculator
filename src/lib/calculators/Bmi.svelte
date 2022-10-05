<script lang="ts">
	export let weight: number;
	export let height: number;
</script>

{#if !isNaN(Math.round((weight / (height * height)) * 10000))}
	<h3 class="pb-0 mb-0">
		BMI: {Math.round((weight / (height * height)) * 10000)} /
		{#if Math.round((weight / (height * height)) * 10000) <= 18.5}
			<span class="under">Untergewicht</span>
		{:else if Math.round((weight / (height * height)) * 10000) <= 24.9}
			<span class="normal">Normalgewicht</span>
		{:else if Math.round((weight / (height * height)) * 10000) <= 29.9}
			<span class="over">Übergewicht</span>
		{:else if Math.round((weight / (height * height)) * 10000) <= 34.9}
			<span class="adi">Adipositas Grad 1</span>
		{:else if Math.round((weight / (height * height)) * 10000) <= 39.9}
			<span class="adi">Adipositas Grad 2</span>
		{:else if Math.round((weight / (height * height)) * 10000) >= 40}
			<span class="adi">Adipositas Grad 3</span>
		{/if}
	</h3>
	<small>* Body Mass Index / Gewicht durch Grösse im Quadrat</small>
{/if}
