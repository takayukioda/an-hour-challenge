<template>
<main id="#main">
	<h1>GitHub Issue Maker</h1>
	<form>
		<label for="token">
			GitHub TOKEN
		</label>
		<input
			type="text"
			name="token"
			v-model="token"
		>
		<label for="title">
			Issue title
		</label>
		<input
			type="text"
			name="title"
			v-model="title"
		>
		<label for="body">
			Issue body
		</label>
		<textarea
			name="body"
			v-model="body"
		>
		</textarea>
		<input
			type="submit"
			value="Make an issue"
		>
	</form>
</main>
</template>

<script>
export default {
	data () {
		return {
			token: '',
			title: '',
			body: '',
		}
	},
	async asyncData() {
	},
}
</script>

<style>
</style>
