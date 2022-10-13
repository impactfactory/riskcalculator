<script lang="ts">
	import { answers } from '$lib/stores';

	export let weight: number;
	export let height: number;
	export let taille: number;
	export let hip: number;
	export let gender: string;
	export let age: number;
</script>

{#if $answers.risk1_6.includes('whr') || $answers.risk1_6.includes('bel') || $answers.risk1_6.includes('bmidge')}
	<fieldset class="radiogroup">
		<div class="gender">
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
		</div>
	</fieldset>
{/if}
<fieldset>
	{#if $answers.risk1_6.includes('whtr') || $answers.risk1_6.includes('bminrc')}
		<label for="age" class="label">
			<span class="label-text">Alter (Jahre)</span>
		</label>
		<input
			name="age"
			type="number"
			step="1"
			min="18"
			max="110"
			class="input input-bordered w-full max-w-xs"
			bind:value={age}
		/>
		<!-- <span class="pl-2">Jahre</span>-->
	{/if}

	{#if $answers.risk1_6.includes('bmiwho') || $answers.risk1_6.includes('bminrc') || $answers.risk1_6.includes('bmidge')}
		<label for="weight" class="label">
			<span class="label-text">Gewicht (kg)</span>
		</label>
		<input
			name="weight"
			type="number"
			step="1"
			class="input input-bordered w-full max-w-xs"
			bind:value={weight}
		/>
		<!--<span class="pl-2">kg</span>-->
	{/if}
	{#if $answers.risk1_6.includes('bmiwho') || $answers.risk1_6.includes('whtr') || $answers.risk1_6.includes('bminrc') || $answers.risk1_6.includes('bmidge')}
		<label for="height" class="label">
			<span class="label-text">Grösse (cm)</span>
		</label>
		<input
			name="height"
			type="number"
			step="1"
			class="input input-bordered w-full max-w-xs"
			bind:value={height}
		/>
		<!-- <span class="pl-2"> cm</span> -->
	{/if}
	{#if $answers.risk1_6.includes('whr')}
		<label for="hip" class="label">
			<span class="label-text">Hüftumfang (cm)</span>
		</label>
		<input
			name="hip"
			type="number"
			step="1"
			class="input input-bordered w-full max-w-xs"
			bind:value={hip}
		/>
		<!-- <span class="pl-2">cm</span>  -->
	{/if}
	{#if $answers.risk1_6.includes('whr') || $answers.risk1_6.includes('whtr') || $answers.risk1_6.includes('bel')}
		<label for="taille" class="label">
			<span class="label-text">Taille (cm)</span>
		</label>
		<input
			name="taille"
			type="number"
			step="1"
			class="input input-bordered w-full max-w-xs"
			bind:value={taille}
		/>
		<!-- <span class="pl-2">cm</span> -->
	{/if}
</fieldset>

<style>
	.gender {
		margin-bottom: 2rem;
	}
	.gender .form-control {
		display: float;
		float: left;
		margin-right: 2rem;
	}
</style>
