<script lang="ts">
	import { fade } from 'svelte/transition';
	import Adi from './messages/Adi.svelte';
	import Norm from './messages/Norm.svelte';
	import Over from './messages/Over.svelte';
	export let taille: number;
	export let hip: number;
	export let gender: string;
</script>

{#if isFinite(parseFloat((taille / hip).toFixed(3))) && taille && hip && gender}
	{@const whr = taille / hip}
	<div in:fade={{ duration: 3000 }}>
		<h3 class="pb-0 mb-0">
			WHR: {whr.toFixed(2)} /
			{#if gender == 'weiblich'}
				{#if whr <= 0.8}
					<Norm />
				{:else if whr > 0.8 && whr <= 0.849}
					<Over />
				{:else if whr > 0.849}
					<Adi />
				{/if}
			{:else if gender == 'männlich'}
				{#if whr <= 0.9}
					<Norm />
				{:else if whr > 0.9 && whr <= 0.99}
					<Over />
				{:else if whr > 0.99}
					<Adi />
				{/if}
			{/if}
		</h3>
		<small
			>* Waist to Hip Ratio / Taille-Umfang durch Hüftumfang. <a
				href="http://apps.who.int/iris/bitstream/handle/10665/44583/9789241501491_eng.pdf;jsessionid=71DEE026302DBDCA957DC0D970598D8B?sequence=1"
				rel="noopener">Quelle Berechnungsmethodik</a
			></small
		>
	</div>
{/if}
