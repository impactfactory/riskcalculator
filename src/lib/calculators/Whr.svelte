<script lang="ts">
	import { answers } from '$lib/stores';

	export let taille: number;
	export let hip: number;
	export let gender: string;
</script>

{#if !isNaN(parseFloat((taille / hip).toFixed(3)))}
	<h3 class="pb-0 mb-0">
		WHR: {parseFloat((taille / hip).toFixed(2))} /
		{#if gender == 'weiblich'}
			{#if parseFloat((taille / hip).toFixed(3)) < 0.8}
				Normalgewicht
			{:else if parseFloat((taille / hip).toFixed(3)) > 0.8 && parseFloat((taille / hip).toFixed(3)) <= 0.84}
				Übergewicht
			{:else if parseFloat((taille / hip).toFixed(3)) > 0.84}
				Adipositas
			{/if}
		{:else if gender == 'männlich'}
			{#if parseFloat((taille / hip).toFixed(3)) < 0.9}
				Normalgewicht
			{:else if parseFloat((taille / hip).toFixed(3)) > 0.9 && parseFloat((taille / hip).toFixed(3)) <= 0.99}
				Übergewicht
			{:else if parseFloat((taille / hip).toFixed(3)) > 0.99}
				Adipositas
			{/if}
		{:else}{/if}
	</h3>
	<small>* Waste to Hip Ratio / Taille-Umfang durch Hüftumfang</small>
{/if}
