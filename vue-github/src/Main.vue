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
		<input
			type="submit"
			value="Make an issue"
			v-on:click="createIssue"
		>
	</form>
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
		async createIssue() {
			if (!this.token || !this.repository) {
				// eslint-disable-next-line
				console.error("No token or repository has been set")
				return
			}
			this.loading = true
			const resp = await axios.post(`https://api.github.com/repos/${this.repository}/issues`, {
				headers: {
					Authorization: this.token,
				},
			})

			// eslint-disable-next-line
			console.log(resp.data)
		}
	},
}
</script>

<style>
</style>
