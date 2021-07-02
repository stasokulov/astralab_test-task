<template>
	<div class="main">
		<div class="main__header">
			<Title :text="title" />
		</div>
		<img class="main__img" src="@/assets/main.png">
	</div>
</template>

<script>
import Title from '@/components/Atoms/Title.vue'

export default {
	name: 'Main',
	components: {
		Title
	},
	props: {
		username: String
	},
	computed: {
		title: function() {
			return `Hello, ${this.username}!`
		}
	}
}
</script>

<style lang="scss">
.main {
	padding-top: 95px;
	&__header {
		max-width: 220px;
		margin: auto;
	}
	&__title {
		margin: 0 0 17px;
	}
	&__img {
		position: fixed;
		bottom: 0;
		left: 0;
		right: 0;
		width: 100%;
		max-height: calc(100% - 190px);
		object-fit: contain;
	}
}
</style>