<script>import axios from 'axios'
export default {
	data() {
		return {
			athanTimes: []
		}
	},
	methods: {
		async getAthanTimes() {
			const res = await axios.get('https://api.aladhan.com/v1/timingsByCity?city=Liverpool&country=Australia')
			this.athanTimes = await res.data.data.timings
		}
	},
	mounted() {
		this.getAthanTimes();
	}
}
</script>

<template>
	<h1>Athan App</h1>
	<ul v-for="(item, index) in athanTimes">{{ index }} : {{ item }}</ul>
</template>