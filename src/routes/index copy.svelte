<script>
	import Exit from '$lib/Exit.svelte';

	let ExitButton = false;
</script>

<Exit {ExitButton} />

<h2 class="font-semibold">Willkommen!</h2>

<p>Berechnen Sie mit unserem Rechner Ihr Risiko an einer Herzkrankheit zu erkranken</p>

<p>
	<strong>P.S.:</strong> Ihre Eingaben bleiben lokal auf Ihrem Computer. Sie werden nirgendwo gespeichert,
	beobachtet oder versendet.
</p>

<a class="my-4 btn btn-primary" href="/fragen/0-0">Beginnen</a>

<style>
	a.btn {
		opacity: 0.9;
	}
</style>
