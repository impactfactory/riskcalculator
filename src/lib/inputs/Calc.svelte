<script lang="ts">
	import Test from './Test.svelte';
	import Data from './Data.svelte';
	import Results from '$lib/Results.svelte';
	export let weight: number;
	export let height: number;
	export let taille: number;
	export let hip: number;
	export let gender: string;
	export let test: string;
	export let age: number;
</script>

<Test bind:test />

<Data bind:weight bind:height bind:taille bind:hip bind:gender bind:age />

<Results bind:age bind:gender bind:hip bind:height bind:taille bind:test bind:weight />
