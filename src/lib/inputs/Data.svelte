<script lang="ts">
	import { answers } from '$lib/stores';

	export let weight: number;
	export let height: number;
	export let taille: number;
	export let hip: number;
	export let gender: string;
	export let age: number;

	let repeats = 100;
</script>

<fieldset>
	<legend class="pb-3">Geben Sie bitte folgendes an:</legend>

	{#if $answers.risk1_6.includes('whr')}
		<legend class="">Geschlecht</legend>
		<div class="form-control">
			<label>
				<input type="radio" class="radio radio-sm" bind:group={gender} value="weiblich" />
				<span class="label-text">weiblich</span>
			</label>
		</div>
		<div class="form-control">
			<label>
				<input type="radio" class="radio radio-sm" bind:group={gender} value="männlich" />
				<span class="label-text">männlich</span>
			</label>
		</div>
	{/if}
	{#if $answers.risk1_6.includes('whtr')}
		<label for="age" class="label">
			<span class="label-text">Alter: {age} Jahre</span>
		</label>

		<input type="range" min="0" max="100" bind:value={age} class="range" step="1" />
		<div class="w-full flex justify-between text-xs px-2">
			{#each { length: 100 } as _, i}
				<span>|</span>
			{/each}
		</div>
	{/if}

	{#if $answers.risk1_6.includes('bmi')}
		<label for="weight" class="label">
			<span class="label-text">Gewicht</span>
		</label>
		<input name="weight" type="number" class="number" bind:value={weight} />
		<span>kg</span>
	{/if}
	{#if $answers.risk1_6.includes('bmi') || $answers.risk1_6.includes('whtr')}
		<label for="height" class="label">
			<span class="label-text">Grösse</span>
		</label>
		<input name="height" type="number" class="number" bind:value={height} />
		<span>cm</span>
	{/if}
	{#if $answers.risk1_6.includes('whr')}
		<label for="hip" class="label">
			<span class="label-text">Hüftumfang</span>
		</label>
		<input name="hip" type="number" class="number" bind:value={hip} />
		<span>cm</span>
	{/if}
	{#if $answers.risk1_6.includes('whr') || $answers.risk1_6.includes('whtr')}
		<label for="taille" class="label">
			<span class="label-text">Taille</span>
		</label>
		<input name="taille" type="number" class="number" bind:value={taille} />
		<span>cm</span>
	{/if}
</fieldset>
