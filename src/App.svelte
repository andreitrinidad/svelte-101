<script>

	// This are regular variables
	let name = 'Andrei';
	let dingdongSize = 'small'
	let firstName = 'Andrei';
	let lastName = 'Trinidad';

	// This are reactive values which updates when something is changed
	$: fullName = `${firstName} ${lastName}`;

	// Suprisingly this works in objects too
	// $: fullName = {
	// 	firstName,
	// 	lastName
	// };

	// And yep, we have reactive statements
	// $: console.log(firstName);

	// Also codeblocks yes, this feels like useEffect in React!!!
	// $: {
	 // code here...

	// }

	const handleDingdong = () => {
		dingdongSize = 'large';
	}

	const handleInput = (e) => {
		dingdongSize = e.target.value;
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>Hey it's ya boi {name}, your dingdong is {dingdongSize}</p>
	<p>Your full name is {fullName} </p>
	<input type="text" bind:value={dingdongSize}>
	<input type="text" bind:value={firstName}>
	<input type="text" bind:value={lastName}>
	<button on:click={handleDingdong}>No my dingdong is LARGE!!!</button>
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