<script lang="ts">
	import { answers } from '$lib/stores';

	export let taille: number;
	export let height: number;
	export let age: number;
</script>

{#if !isNaN(parseFloat((taille / height).toFixed(3)))}
	<h3 class="pb-0 mb-0">
		WHtR: {parseFloat((taille / height).toFixed(2))} /

		{#if age < 15}
			{#if parseFloat((taille / height).toFixed(3)) <= 0.34}
				Untergewicht
			{:else if parseFloat((taille / height).toFixed(3)) > 0.34 && parseFloat((taille / height).toFixed(3)) <= 0.45}
				Normalgewicht
			{:else if parseFloat((taille / height).toFixed(3)) > 0.45 && parseFloat((taille / height).toFixed(3)) <= 0.51}
				Übergewicht
			{:else if parseFloat((taille / height).toFixed(3)) > 0.52}
				Adipositas
			{/if}
		{:else if age >= 15 && age <= 40}
			{#if parseFloat((taille / height).toFixed(3)) <= 0.4}
				Untergewicht
			{:else if parseFloat((taille / height).toFixed(3)) > 0.4 && parseFloat((taille / height).toFixed(3)) <= 0.5}
				Normalgewicht
			{:else if parseFloat((taille / height).toFixed(3)) > 0.5 && parseFloat((taille / height).toFixed(3)) <= 0.56}
				Übergewicht
			{:else if parseFloat((taille / height).toFixed(3)) > 0.57}
				Adipositas
			{/if}
		{:else if age > 40}
			{#if parseFloat((taille / height).toFixed(3)) <= 0.4}
				Untergewicht
			{:else if parseFloat((taille / height).toFixed(3)) > 0.4 && parseFloat((taille / height).toFixed(3)) <= 0.6}
				Normalgewicht
			{:else if parseFloat((taille / height).toFixed(3)) > 0.6 && parseFloat((taille / height).toFixed(3)) <= 0.66}
				Übergewicht
			{:else if parseFloat((taille / height).toFixed(3)) > 0.67}
				Adipositas
			{/if}
		{/if}
	</h3>
	<small>* Waste to Height Ratio / Umfang Taille durch Körpergrösse</small>
{/if}

<!--
    Studie: https://idw-online.de/en/attachmentdata2347.pdf
    https://de.wikipedia.org/wiki/Waist-to-Height_Ratio

    Für unter 40-Jährige ist ein Wert über 0,5 kritisch.
Bei den 40-50-Jährigen verschiebt sich der Grenzwert von 0,5 um 0,01 pro Lebensjahr nach oben, z. B. 40 Jahre bis 0,5; 41 Jahre bis 0,51; 42 Jahre bis 0,52 usw.
Bei über 50-Jährigen sollte der Wert 0,6 nicht überschreiten.
-->
