<script lang="ts">
	import { answers } from '$lib/stores';
	export let weight: number;
	export let height: number;
</script>

{#if !isNaN(Math.round((weight / (height * height)) * 10000))}
	<h3 class="pb-0 mb-0">
		BMI: {Math.round((weight / (height * height)) * 10000)} / Stufe:
		{#if Math.round((weight / (height * height)) * 10000) <= 18.5}
			untergewichtig
		{:else if Math.round((weight / (height * height)) * 10000) <= 24.9}
			Normalgewicht
		{:else if Math.round((weight / (height * height)) * 10000) <= 29.9}
			übergewichtig
		{:else if Math.round((weight / (height * height)) * 10000) <= 34.9}
			Adipositas Grad 1
		{:else if Math.round((weight / (height * height)) * 10000) <= 39.9}
			Adipositas Grad 2
		{:else if Math.round((weight / (height * height)) * 10000) >= 40}
			Adipositas Grad 3
		{/if}
	</h3>
	<small>* Body Mass Index / Gewicht durch Grösse im Quadrat</small>
{/if}
