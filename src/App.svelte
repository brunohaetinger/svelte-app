<script>
	import Stepper from './Stepper.svelte';
	export let name;
	let stepperValue = 0;
	$: isEven = stepperValue % 2 == 0;

	function handleStepperEvents(event){
		console.log(event);
		const value = event.detail.value;
		if(value === '-'){ 
			stepperValue--;
		}else {
			stepperValue++;
		}
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<Stepper on:btnValue={handleStepperEvents} value={stepperValue}></Stepper>

	{#if isEven}
		<h1>{stepperValue} is EVEN!</h1>
	{:else}
		<h1>{stepperValue} is ODD!</h1>
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