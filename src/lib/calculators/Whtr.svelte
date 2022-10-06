<script lang="ts">
	import { answers } from '$lib/stores';

	export let taille: number;
	export let height: number;
	export let age: number;
</script>

{#if !isNaN((taille / height).toFixed(3))}
	{@const whtr = taille / height}
	<h3 class="pb-0 mb-0">
		WHtR: {whtr.toFixed(5)} /

		{#if age <= 15}
			{#if whtr <= 0.34}
				<span class="under">Untergewicht</span>
			{:else if whtr >= 0.34 && whtr <= 0.4599}
				<span class="normal">Normalgewicht</span>
			{:else if whtr >= 0.46 && whtr <= 0.5199}
				<span class="over">Übergewicht (Präadipositas)</span>
			{:else if whtr >= 0.52 && whtr <= 0.63}
				<span class="adi">Adipositas I (krankhaftes Übergewicht)</span>
			{:else if whtr > 0.63}
				<span class="adi">Adipositas II-III (krankhaft bis morbides Übergewicht)</span>
			{/if}
		{:else if age >= 16 && age <= 40}
			{#if whtr < 0.4}
				<span class="under">Untergewicht</span>
			{:else if whtr >= 0.4 && whtr <= 0.599}
				<span class="normal">Normalgewicht</span>
			{:else if whtr >= 0.51 && whtr <= 0.5699}
				<span class="over">Übergewicht (Präadipositas)</span>
			{:else if whtr >= 0.57 && whtr <= 0.68}
				<span class="adi">Adipositas I (krankhaftes Übergewicht)</span>
			{:else if whtr > 0.68}
				<span class="adi">Adipositas II-III (krankhaft bis morbides Übergewicht)</span>
			{/if}
		{:else if (age = 41)}
			{#if whtr < 0.4}
				<span class="under">Untergewicht</span>
			{:else if whtr >= 0.4 && whtr <= 0.5199}
				<span class="normal">Normalgewicht</span>
			{:else if whtr >= 0.52 && whtr <= 0.5799}
				<span class="over">Übergewicht (Präadipositas)</span>
			{:else if whtr >= 0.58 && whtr <= 0.69}
				<span class="adi">Adipositas I (krankhaftes Übergewicht)</span>
			{:else if whtr > 0.69}
				<span class="adi">Adipositas II-III (krankhaft bis morbides Übergewicht)</span>
			{/if}
		{:else if (age = 42)}
			{#if whtr < 0.4}
				<span class="under">Untergewicht</span>
			{:else if whtr >= 0.4 && whtr <= 0.5299}
				<span class="normal">Normalgewicht</span>
			{:else if whtr >= 0.53 && whtr <= 0.5899}
				<span class="over">Übergewicht (Präadipositas)</span>
			{:else if whtr >= 0.59 && whtr <= 0.7}
				<span class="adi">Adipositas I (krankhaftes Übergewicht)</span>
			{:else if whtr > 0.7}
				<span class="adi">Adipositas II-III (krankhaft bis morbides Übergewicht)</span>
			{/if}
		{:else if (age = 43)}
			{#if whtr < 0.4}
				<span class="under">Untergewicht</span>
			{:else if whtr >= 0.4 && whtr <= 0.5399}
				<span class="normal">Normalgewicht</span>
			{:else if whtr >= 0.54 && whtr <= 0.5999}
				<span class="over">Übergewicht (Präadipositas)</span>
			{:else if whtr >= 0.6 && whtr <= 0.71}
				<span class="adi">Adipositas I (krankhaftes Übergewicht)</span>
			{:else if whtr > 0.71}
				<span class="adi">Adipositas II-III (krankhaft bis morbides Übergewicht)</span>
			{/if}
		{:else if (age = 44)}
			{#if whtr < 0.4}
				<span class="under">Untergewicht</span>
			{:else if whtr >= 0.4 && whtr <= 0.5499}
				<span class="normal">Normalgewicht</span>
			{:else if whtr >= 0.55 && whtr <= 0.699}
				<span class="over">Übergewicht (Präadipositas)</span>
			{:else if whtr >= 0.61 && whtr <= 0.72}
				<span class="adi">Adipositas I (krankhaftes Übergewicht)</span>
			{:else if whtr > 0.72}
				<span class="adi">Adipositas II-III (krankhaft bis morbides Übergewicht)</span>
			{/if}
		{:else if (age = 45)}
			{#if whtr < 0.4}
				<span class="under">Untergewicht</span>
			{:else if whtr >= 0.4 && whtr <= 0.5599}
				<span class="normal">Normalgewicht</span>
			{:else if whtr >= 0.56 && whtr <= 0.6199}
				<span class="over">Übergewicht (Präadipositas)</span>
			{:else if whtr >= 0.62 && whtr <= 0.73}
				<span class="adi">Adipositas I (krankhaftes Übergewicht)</span>
			{:else if whtr > 0.73}
				<span class="adi">Adipositas II-III (krankhaft bis morbides Übergewicht)</span>
			{/if}
		{:else if (age = 46)}
			{#if whtr < 0.4}
				<span class="under">Untergewicht</span>
			{:else if whtr >= 0.4 && whtr <= 0.5699}
				<span class="normal">Normalgewicht</span>
			{:else if whtr >= 0.57 && whtr <= 0.6299}
				<span class="over">Übergewicht (Präadipositas)</span>
			{:else if whtr >= 0.63 && whtr <= 0.74}
				<span class="adi">Adipositas I (krankhaftes Übergewicht)</span>
			{:else if whtr > 0.74}
				<span class="adi">Adipositas II-III (krankhaft bis morbides Übergewicht)</span>
			{/if}
		{:else if (age = 47)}
			{#if whtr < 0.4}
				<span class="under">Untergewicht</span>
			{:else if whtr >= 0.4 && whtr <= 0.5799}
				<span class="normal">Normalgewicht</span>
			{:else if whtr >= 0.58 && whtr <= 0.6399}
				<span class="over">Übergewicht (Präadipositas)</span>
			{:else if whtr >= 0.64 && whtr <= 0.75}
				<span class="adi">Adipositas I (krankhaftes Übergewicht)</span>
			{:else if whtr > 0.75}
				<span class="adi">Adipositas II-III (krankhaft bis morbides Übergewicht)</span>
			{/if}
		{:else if (age = 48)}
			{#if whtr < 0.4}
				<span class="under">Untergewicht</span>
			{:else if whtr >= 0.4 && whtr <= 0.5899}
				<span class="normal">Normalgewicht</span>
			{:else if whtr >= 0.59 && whtr <= 0.6499}
				<span class="over">Übergewicht (Präadipositas)</span>
			{:else if whtr >= 0.65 && whtr <= 0.76}
				<span class="adi">Adipositas I (krankhaftes Übergewicht)</span>
			{:else if whtr > 0.76}
				<span class="adi">Adipositas II-III (krankhaft bis morbides Übergewicht)</span>
			{/if}
		{:else if (age = 49)}
			{#if whtr < 0.4}
				<span class="under">Untergewicht</span>
			{:else if whtr >= 0.4 && whtr <= 0.5999}
				<span class="normal">Normalgewicht</span>
			{:else if whtr >= 0.6 && whtr <= 0.6599}
				<span class="over">Übergewicht (Präadipositas)</span>
			{:else if whtr >= 0.66 && whtr <= 0.77}
				<span class="adi">Adipositas I (krankhaftes Übergewicht)</span>
			{:else if whtr > 0.77}
				<span class="adi">Adipositas II-III (krankhaft bis morbides Übergewicht)</span>
			{/if}
		{:else if age >= 50}
			{#if whtr < 0.4}
				<span class="under">Untergewicht</span>
			{:else if whtr >= 0.4 && whtr <= 0.699}
				<span class="normal">Normalgewicht</span>
			{:else if whtr >= 0.61 && whtr <= 0.6699}
				<span class="over">Übergewicht (Präadipositas)</span>
			{:else if whtr >= 0.67 && whtr <= 0.78}
				<span class="adi">Adipositas I (krankhaftes Übergewicht)</span>
			{:else if whtr > 0.78}
				<span class="adi">Adipositas II-III (krankhaft bis morbides Übergewicht)</span>
			{/if}
		{/if}
	</h3>
	<small
		>* Waste to Height Ratio / Umfang Taille durch Körpergrösse / <a
			href="https://www.mercedes-benz-bkk.com/gesundheit/ernaehrung/whtr"
			rel="noopener">Quelle Berechnungsmethodik</a
		></small
	>
{/if}
