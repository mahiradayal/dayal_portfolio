<script>
	import inspections from './inspections.json';
	// Keep: npm install @rollup/plugin-json --save-dev
	let selectedInspection;
</script>

<main>
	{#if selectedInspection}
		<p><a on:click={() => selectedInspection = null} href='#'>Return to list</a></p>
		<h1>Name is {selectedInspection.ffl_proprietor_2}</h1>
		<h2>The state is {selectedInspection.ffl_state}</h2>
	{:else}
	<ul>
		<h3> Gun Inspections List — Select to Learn More</h3>
		{#each inspections as inspection}
			<li on:click={() => selectedInspection = inspection}>{inspection.ffl_proprietor_2}</li>
		{/each}
	</ul>
    {/if}

</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>