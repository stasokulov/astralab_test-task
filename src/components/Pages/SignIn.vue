<template>
	<div class="sign-in">
		<Title text="Sign In" />
		<Form button_text="Sign Up" class="form" @submit="$emit('login')">
			<Input type="email" placeholder="your@email.com" title="Email" class=""/>
			<Input type="password" placeholder="Password" title="Password" class=""/>
		</Form>
		<Footer text="Don’t have an account yet?"
			text_link="Sign Up"
			@click-on-link="$emit('sign_up')"
		/>
	</div>
</template>

<script>
import Form from '@/components/Molecules/Form.vue'
import Input from '@/components/Atoms/Input.vue'
import Title from '@/components/Atoms/Title.vue'
import Footer from '@/components/Atoms/Footer.vue'

export default {
	name: 'SignIn',
	components: {
		Form,
		Title,
		Input,
		Footer
	}
}
</script>

<style scoped lang="scss">
.form {
	margin-bottom: 20px;
}
</style>