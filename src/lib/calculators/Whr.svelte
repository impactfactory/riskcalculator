<script lang="ts">
	export let taille: number;
	export let hip: number;
	export let gender: string;
</script>

{#if isFinite(parseFloat((taille / hip).toFixed(3)))}
	{@const whr = taille / hip}
	<h3 class="pb-0 mb-0">
		WHR: {whr.toFixed(2)} /
		{#if gender == 'weiblich'}
			{#if whr <= 0.8}
				<span class="normal">Normalgewicht</span>
			{:else if whr > 0.8 && whr <= 0.849}
				<span class="over">Übergewicht</span>
			{:else if whr > 0.849}
				<span class="adi">Adipositas</span>
			{/if}
		{:else if gender == 'männlich'}
			{#if whr <= 0.9}
				<span class="normal">Normalgewicht</span>
			{:else if whr > 0.9 && whr <= 0.99}
				<span class="over">Übergewicht</span>
			{:else if whr > 0.99}
				<span class="adi">Adipositas</span>
			{/if}
		{/if}
	</h3>
	<small
		>* Waste to Hip Ratio / Taille-Umfang durch Hüftumfang. <a
			href="http://apps.who.int/iris/bitstream/handle/10665/44583/9789241501491_eng.pdf;jsessionid=71DEE026302DBDCA957DC0D970598D8B?sequence=1"
			rel="noopener">Quelle Berechnungsmethodik</a
		></small
	>
{/if}
