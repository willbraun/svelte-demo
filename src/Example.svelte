<script lang="ts">
	let firstName: string = 'Will'
	let lastName: string = 'Braun'
	let color: string = 'blue'
	let showText: boolean = false
	let users: { id: string; name: string }[] = [
		{
			id: '1',
			name: 'John',
		},
		{
			id: '2',
			name: 'Bill',
		},
		{
			id: '3',
			name: 'Steve',
		},
	]

	$: name = firstName + ' ' + lastName // $: is a reactive value - updates

	const toggle = () => {
		color = color === 'blue' ? 'red' : 'blue'
		showText = !showText
		users = [...users, { id: '4', name: 'Jen' }]
	}
</script>

<main>
	<h1 style="color: {color}">Hello {name}</h1>
	{#if showText}
		<p>Look at me</p>
	{:else}
		<p>Don't look at me</p>
	{/if}

	<button on:click={toggle}>Click me</button>

	{#each users as user (user.id)}
		<h3>{user.id}: {user.name}</h3>
	{/each}
</main>

<style>
</style>
