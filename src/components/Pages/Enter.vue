<template>
	<div class="enter">
		<div class="enter__header">
			<Title text="Ready for a great User experience?" />
			<p class="enter__subtitle">Bring your media to the next level!</p>
		</div>
		<div class="enter__buttons">
			<Button class="enter__sign-button"
				@click.native="$emit('sign_up')"
				text="Sign Up"
				:dark="false"
				:disable="false"
				:max_form="false"
			/>
			<button class="round-button" @click="$emit('sign_in')"></button>
		</div>
		<img class="enter__img" src="@/assets/enter.png">
	</div>
</template>

<script>
import Button from '@/components/Atoms/Button.vue'
import Title from '@/components/Atoms/Title.vue'

export default {
	name: 'SignUp',
	components: {
		Title,
		Button
	}
}
</script>

<style lang="scss">
.enter {

	&__header {
		max-width: 220px;
		margin: auto;
	}
	&__title {
		margin: 0 0 17px;
	}
	&__subtitle {
		margin: 0 0 27px;
		font-family: 'Inter', sans-serif;
		font-style: normal;
		font-weight: normal;
		font-size: 14px;
		line-height: 20px;
		text-align: center;
		letter-spacing: 0.02em;
		color: #3E4462;
	}
	&__buttons {
		display: flex;
		max-width: 184px;
		margin: auto;
	}
	&__sign-button {
		margin-right: 16px;
	}
	&__img {
		position: fixed;
		bottom: 0;
		left: 0;
		right: 0;
		width: 100%;
		max-height: calc(100% - 282px);
		object-fit: contain;
	}
}
.round-button {
	width: 48px;
	height: 48px;
	border: none;
	border-radius: 50%;
	background-color: #1E1A3E;
	background-image: url("data:image/svg+xml,%3Csvg width='16' height='14' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M1 8h11.2l-4 3.9a1 1 0 000 1.4c.5.4 1.1.4 1.5 0l5.6-5.6c.4-.4.4-1 0-1.4L9.7.7a1 1 0 10-1.4 1.4L12.2 6H1a1 1 0 00-1 1c0 .5.5 1 1 1z' fill='%23fff'/%3E%3C/svg%3E");
	background-position: center;
	background-repeat: no-repeat;
	background-size: 16px 13px;
	cursor: pointer;
}
</style>