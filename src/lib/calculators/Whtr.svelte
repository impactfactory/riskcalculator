<script lang="ts">
	import { answers } from '$lib/stores';
	import { fade } from 'svelte/transition';
	import Adi1 from './messages/Adi1.svelte';
	import Adi23 from './messages/Adi23.svelte';
	import Norm from './messages/Norm.svelte';
	import Over from './messages/Over.svelte';
	import Under from './messages/Under.svelte';
	export let taille: number;
	export let height: number;
	export let age: number;
</script>

{#if !isNaN((taille / height).toFixed(3)) && age && taille && height}
	{@const whtr = taille / height}
	<div in:fade={{ duration: 3000 }}>
		<h3 class="pb-0 mb-0">
			WHtR: {whtr.toFixed(1)} /

			{#if age <= 15}
				{#if whtr <= 0.34}
					<Under />
				{:else if whtr >= 0.34 && whtr <= 0.4599}
					<Norm />
				{:else if whtr >= 0.46 && whtr <= 0.5199}
					<Over />
				{:else if whtr >= 0.52 && whtr <= 0.63}
					<Adi1 />
				{:else if whtr > 0.63}
					<Adi23 />
				{/if}
			{:else if age >= 16 && age <= 40}
				{#if whtr < 0.4}
					<Under />
				{:else if whtr >= 0.4 && whtr <= 0.599}
					<Norm />
				{:else if whtr >= 0.51 && whtr <= 0.5699}
					<Over />
				{:else if whtr >= 0.57 && whtr <= 0.68}
					<Adi1 />
				{:else if whtr > 0.68}
					<Adi23 />
				{/if}
			{:else if (age = 41)}
				{#if whtr < 0.4}
					<Under />
				{:else if whtr >= 0.4 && whtr <= 0.5199}
					<Norm />
				{:else if whtr >= 0.52 && whtr <= 0.5799}
					<Over />
				{:else if whtr >= 0.58 && whtr <= 0.69}
					<Adi1 />
				{:else if whtr > 0.69}
					<Adi23 />
				{/if}
			{:else if (age = 42)}
				{#if whtr < 0.4}
					<Under />
				{:else if whtr >= 0.4 && whtr <= 0.5299}
					<Norm />
				{:else if whtr >= 0.53 && whtr <= 0.5899}
					<Over />
				{:else if whtr >= 0.59 && whtr <= 0.7}
					<Adi1 />
				{:else if whtr > 0.7}
					<Adi23 />
				{/if}
			{:else if (age = 43)}
				{#if whtr < 0.4}
					<Under />
				{:else if whtr >= 0.4 && whtr <= 0.5399}
					<Norm />
				{:else if whtr >= 0.54 && whtr <= 0.5999}
					<Over />
				{:else if whtr >= 0.6 && whtr <= 0.71}
					<Adi1 />
				{:else if whtr > 0.71}
					<Adi23 />
				{/if}
			{:else if (age = 44)}
				{#if whtr < 0.4}
					<Under />
				{:else if whtr >= 0.4 && whtr <= 0.5499}
					<Norm />
				{:else if whtr >= 0.55 && whtr <= 0.699}
					<Over />
				{:else if whtr >= 0.61 && whtr <= 0.72}
					<Adi1 />
				{:else if whtr > 0.72}
					<Adi23 />
				{/if}
			{:else if (age = 45)}
				{#if whtr < 0.4}
					<Under />
				{:else if whtr >= 0.4 && whtr <= 0.5599}
					<Norm />
				{:else if whtr >= 0.56 && whtr <= 0.6199}
					<Over />
				{:else if whtr >= 0.62 && whtr <= 0.73}
					<Adi1 />
				{:else if whtr > 0.73}
					<Adi23 />
				{/if}
			{:else if (age = 46)}
				{#if whtr < 0.4}
					<Under />
				{:else if whtr >= 0.4 && whtr <= 0.5699}
					<Norm />
				{:else if whtr >= 0.57 && whtr <= 0.6299}
					<Over />
				{:else if whtr >= 0.63 && whtr <= 0.74}
					<Adi1 />
				{:else if whtr > 0.74}
					<Adi23 />
				{/if}
			{:else if (age = 47)}
				{#if whtr < 0.4}
					<Under />
				{:else if whtr >= 0.4 && whtr <= 0.5799}
					<Norm />
				{:else if whtr >= 0.58 && whtr <= 0.6399}
					<Over />
				{:else if whtr >= 0.64 && whtr <= 0.75}
					<Adi1 />
				{:else if whtr > 0.75}
					<Adi23 />
				{/if}
			{:else if (age = 48)}
				{#if whtr < 0.4}
					<Under />
				{:else if whtr >= 0.4 && whtr <= 0.5899}
					<Norm />
				{:else if whtr >= 0.59 && whtr <= 0.6499}
					<Over />
				{:else if whtr >= 0.65 && whtr <= 0.76}
					<Adi1 />
				{:else if whtr > 0.76}
					<Adi23 />
				{/if}
			{:else if (age = 49)}
				{#if whtr < 0.4}
					<Under />
				{:else if whtr >= 0.4 && whtr <= 0.5999}
					<Norm />
				{:else if whtr >= 0.6 && whtr <= 0.6599}
					<Over />
				{:else if whtr >= 0.66 && whtr <= 0.77}
					<Adi1 />
				{:else if whtr > 0.77}
					<Adi23 />
				{/if}
			{:else if age >= 50}
				{#if whtr < 0.4}
					<Under />
				{:else if whtr >= 0.4 && whtr <= 0.699}
					<Norm />
				{:else if whtr >= 0.61 && whtr <= 0.6699}
					<Over />
				{:else if whtr >= 0.67 && whtr <= 0.78}
					<Adi1 />
				{:else if whtr > 0.78}
					<Adi23 />
				{/if}
			{/if}
		</h3>
		<small
			>* Waste to Height Ratio / Umfang Taille durch Körpergrösse / <a
				href="https://www.mercedes-benz-bkk.com/gesundheit/ernaehrung/whtr"
				rel="noopener">Quelle Berechnungsmethodik</a
			></small
		>
	</div>
{/if}
