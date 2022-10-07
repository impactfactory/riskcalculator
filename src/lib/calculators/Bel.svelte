<script lang="ts">
	import { fade } from 'svelte/transition';
	import Norm from './messages/Norm.svelte';
	import Over from './messages/Over.svelte';
	export let taille: number;
	export let gender: string;
</script>

{#if taille && gender}
	<div in:fade={{ duration: 3000 }}>
		<h3 class="pb-0 mb-0">
			Bauchumfang: {taille} cm /
			{#if gender == 'weiblich'}
				{#if taille <= 80}
					<Norm />
				{:else if taille > 80 && taille <= 88}
					<Over />
				{:else if taille > 88}
					<span class="adi">erhöhtes Gesundheitsrisiko!</span>
				{/if}
			{:else if gender == 'männlich'}
				{#if taille <= 94}
					<span class="normal">
						<Norm />
					</span>
				{:else if taille > 94 && taille <= 102}
					<Over />
				{:else if taille > 102}
					<span class="adi">erhöhtes Gesundheitsrisiko!</span>
				{/if}
			{/if}
		</h3>
	</div>
{/if}
