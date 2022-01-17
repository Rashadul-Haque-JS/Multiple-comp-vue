<template>
	<div class="wrapper" v-if="!cachedCookie">

		{{alert('accept cookie')}}
	</div>
</template>

<script>
export default {
	data() {
		return {
			cachedCookie: null,
           
		};
	},
	methods: {
		checkCookies() {
			this.cachedCookie = false;
			localStorage.setItem("acceptedCookie", true);
		},
	},
	created() {
		this.cachedCookie = JSON.parse(localStorage.getItem("acceptedCookie"));
		
	},
};
</script>

<style scoped>
div.wrapper {
	border-radius: 1rem;
	background: rgba(220, 20, 20, 0.705);
	width: 35rem;
	height: 25rem;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
}
</style>