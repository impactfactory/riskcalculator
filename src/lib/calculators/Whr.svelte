<script lang="ts">
	export let taille: number;
	export let hip: number;
	export let gender: string;
</script>

{#if isFinite(parseFloat((taille / hip).toFixed(3)))}
	<h3 class="pb-0 mb-0">
		WHR: {parseFloat((taille / hip).toFixed(2))} /
		{#if gender == 'weiblich'}
			{#if parseFloat((taille / hip).toFixed(3)) <= 0.8}
				<span class="normal">Normalgewicht</span>
			{:else if parseFloat((taille / hip).toFixed(3)) > 0.8 && parseFloat((taille / hip).toFixed(3)) <= 0.84}
				<span class="over">Übergewicht</span>
			{:else if parseFloat((taille / hip).toFixed(3)) > 0.84}
				<span class="adi">Adipositas</span>
			{/if}
		{:else if gender == 'männlich'}
			{#if parseFloat((taille / hip).toFixed(3)) <= 0.9}
				<span class="normal">Normalgewicht</span>
			{:else if parseFloat((taille / hip).toFixed(3)) > 0.9 && parseFloat((taille / hip).toFixed(3)) <= 0.99}
				<span class="over">Übergewicht</span>
			{:else if parseFloat((taille / hip).toFixed(3)) > 0.99}
				<span class="adi">Adipositas</span>
			{/if}
		{:else}{/if}
	</h3>
	<small>* Waste to Hip Ratio / Taille-Umfang durch Hüftumfang</small>
{/if}
