<template>
	<form class="form" @submit.prevent="$emit('submit')">
		<div class="form__fields">
			<slot></slot>
		</div>
		<Button :text="button_text" :dark="true" :disable="false" :max_form="true"/>	
	</form>
</template>

<script>
import Button from '@/components/Atoms/Button.vue'

export default {
	name: 'Form',
	components: {
		Button
	},
	props: {
		button_text: {
			type: String,
			default: 'Go!'
		}
	}
}
</script>

<style lang="scss">
.form {
	padding: 23px 22px 18px;
	background: #fff;
	border-radius: 40px;

	&__fields {
		padding-bottom: 39px;
	}
}
</style>