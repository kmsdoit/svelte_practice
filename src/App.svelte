<script>
	let name = ""
	let age = 0
	let userId = 0
	let company = ""

	const handleSubmit = async() => {

		const data = {
			"userid": userId,
			"name" : name,
			"age" : age,
			"company" : company
		}

		const postFetch = await fetch(`http://localhost:8000/user/${userId}`,{
			method : "POST",
			headers: {'Content-Type': 'application/json'},
			body: JSON.stringify(data)
		});

		const postFetchingJson = await postFetch.json();

		console.log(postFetchingJson)

	}
</script>

<main>
	<form on:submit|preventDefault={handleSubmit}>
		<input class="form" type="text" bind:value={userId}/>
		<input class="form" type="text" bind:value={name}/>
		<input class="form" type="text" bind:value={age}/>
		<input class="form" type="text" bind:value={company}/>
		<input class="form" type="submit"/>
	</form>
</main>

<style>

</style>
