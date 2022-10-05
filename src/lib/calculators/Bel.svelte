<script lang="ts">
	export let taille: number;
	export let gender: string;
</script>

{#if taille !== null}
	<h3 class="pb-0 mb-0">
		Bauchumfang: {taille} cm /
		{#if gender == 'weiblich'}
			{#if taille <= 80}
				<span class="normal">Normalgewicht</span>
			{:else if taille > 80}
				<span class="over">Übergewicht</span>
			{:else if taille > 88}
				<span class="adi">Adipositas</span>
			{/if}
		{:else if gender == 'männlich'}
			{#if taille <= 94}
				<span class="normal">Normalgewicht</span>
			{:else if taille > 94}
				<span class="over">Übergewicht</span>
			{:else if taille > 102}
				<span class="adi">Adipositas</span>
			{/if}
		{/if}
	</h3>
{/if}
