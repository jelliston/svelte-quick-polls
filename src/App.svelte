<!--Started NetNinja Tutorial but stopped at #6 to look into networking-->
<script>
	let firstName = 'Mario';
	let lastName = 'Lopez';
	let beltColor = 'black';
	
	// Reactive values in Svelte watch other values and update when they change
	$: fullName = `${firstName} ${lastName}`;

	// Reactive statements run whenever data inside the statement changes
	$: {
	console.log(beltColor);
	console.log(fullName);
	}
	
	const handleClick = () => {
		beltColor = 'orange';
	}
	const handleInput = (e) => {
		beltColor = e.target.value;
	}
</script>

<main>
	<p>{fullName} - {beltColor} belt!</p>
	<input type="text" bind:value={firstName}>
	<input type="text" bind:value={lastName}>
	<input type="text" bind:value={beltColor}> <!-- bind:value is a svelte key word for 2-way data binding-->
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