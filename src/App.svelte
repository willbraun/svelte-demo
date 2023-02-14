<script lang="ts">
	// if not using stores, put data in top level component "App.svelte" and pass down to other components as props

	import FeedbackList from './components/FeedbackList.svelte'

	let feedback: { id: string; rating: string; text: string }[] = [
		{
			id: '1',
			rating: '7',
			text: 'qwer qewr qwer qwerqwerqwer qwer qwer qwerqwer wqer qwer',
		},
		{
			id: '2',
			rating: '9',
			text: 'asdf asdfasdf asdf asdf asdfasdfasd asdfasdf asdfasdfa sdfasdf',
		},
		{
			id: '3',
			rating: '5',
			text: 'xcvbxcvb xcvb xcvb cxvbxccxvb c c cv c xcvb xcvb cvbxcvbxc vbcvb cxvb',
		},
	]

	const deleteFeedback = e => {
		const itemId = e.detail
		feedback = feedback.filter(item => item.id !== itemId)
	}
</script>

<main class="container">
	<FeedbackList {feedback} on:delete-feedback={deleteFeedback} />
</main>
