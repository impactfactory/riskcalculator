<script lang="ts">
	export let test: string;
</script>

<h2>Wählen Sie die Methode:</h2>

<fieldset class="checkboxgroup">
	<div class="form-control">
		<label class="cursor-pointer">
			<input type="checkbox" class="checkbox checkbox-sm" value="whtr" bind:group={test} />
			<div class="tooltip tooltip-open tooltip-right tooltip-success" data-tip="empfohlen!">
				<span class="label-text">WHtR (Waste to Height Ratio)</span>
			</div>
		</label>
	</div>
	<div class="form-control">
		<label class="cursor-pointer">
			<input type="checkbox" class="checkbox checkbox-sm" value="bmi" bind:group={test} />
			<span class="label-text">BMI (Body Mass Index)</span>
		</label>
	</div>
	<div class="form-control">
		<label class="cursor-pointer">
			<input type="checkbox" class="checkbox checkbox-sm" value="whr" bind:group={test} />
			<span class="label-text">WHR (Waste to Hip Ratio)</span>
		</label>
	</div>
</fieldset>

<style>
	fieldset {
		border-bottom: 1px dashed var(--bodycolor);
		border-top: 1px dashed var(--bodycolor);
		padding: 0.5rem 0 1rem 0;
	}
</style>
