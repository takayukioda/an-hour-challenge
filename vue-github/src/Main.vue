<template>
<main id="#main">
	<h1>GitHub Issue Maker</h1>
	<label for="token">
		GitHub TOKEN
	</label>
	<input
		type="text"
		name="token"
		v-model="token"
	>
	<label for="repository">
		Repository
	</label>
	<input
		type="text"
		name="repository"
		placeholder=":owner/:repo"
		v-model="repository"
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
	<button
		v-on:click="createIssue"
	>
		Make an issue
	</button>
</main>
</template>

<script>
import axios from 'axios'

export default {
	data() {
		return {
			loading: false,
			token: '',
			title: '',
			body: '',
			repository: '',
		}
	},
	methods: {
		createIssue() {
			if (!this.token || !this.repository) {
				// eslint-disable-next-line
				console.error("No token or repository has been set")
				return
			}
			this.loading = true
			axios.post(`https://api.github.com/repos/${this.repository}/issues`, {
				title: this.title,
				body: this.body,
			}, {
				headers: {
					Authorization: `Bearer ${this.token}`,
				},
			}).then((resp) => {
				// eslint-disable-next-line
				console.log(resp.data)
			})
		}
	},
}
</script>

<style>
</style>
