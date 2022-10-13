<script lang="ts">
	export let test: any;
</script>

<h3>Berechnungs-Methode:</h3>

<fieldset class="checkboxgroup">
	<div class="form-control">
		<label class="cursor-pointer">
			<input type="checkbox" class="checkbox checkbox-sm" value="whtr" bind:group={test} />
			<div class="tooltip tooltip-open tooltip-right tooltip-success" data-tip="empfohlen!">
				<span class="label-text">WHtR &nbsp;&nbsp;</span>
			</div>
		</label>
	</div>
	<div class="form-control">
		<label class="cursor-pointer">
			<input type="checkbox" class="checkbox checkbox-sm" value="bmiwho" bind:group={test} />
			<span class="label-text">BMI (WHO)</span>
		</label>
	</div>
	<div class="form-control">
		<label class="cursor-pointer">
			<input type="checkbox" class="checkbox checkbox-sm" value="bmidge" bind:group={test} />
			<span class="label-text">BMI DGE (deutsch)</span>
		</label>
	</div>
	<div class="form-control">
		<label class="cursor-pointer">
			<input type="checkbox" class="checkbox checkbox-sm" value="bminrc" bind:group={test} />
			<span class="label-text">BMI NRC (amerikanisch)</span>
		</label>
	</div>
	<div class="form-control">
		<label class="cursor-pointer">
			<input type="checkbox" class="checkbox checkbox-sm" value="whr" bind:group={test} />
			<span class="label-text">WHR</span>
		</label>
	</div>
	<div class="form-control">
		<label class="cursor-pointer">
			<input type="checkbox" class="checkbox checkbox-sm" value="bel" bind:group={test} />
			<span class="label-text">Bauchumfang-Test</span>
		</label>
	</div>
</fieldset>

<style>
	fieldset {
		border-bottom: 1px dashed var(--bodycolor);
		border-top: 1px dashed var(--bodycolor);
		padding: 0.5rem 0 1rem 0;
		width: 100%;
	}
</style>
