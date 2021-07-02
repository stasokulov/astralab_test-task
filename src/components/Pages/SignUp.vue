<template>
	<div class="sign-up">
		<Title text="Sign Up" />
		<Form button_text="Sign Up" class="form" @submit="$emit('register')">
			<Input type="text" placeholder="Your Name" title="Full name" class=""/>
			<Input type="email" placeholder="your@email.com" title="Email" class=""/>
			<Input type="password" placeholder="Password" title="Password" prompt="Password must contain 8+ symbols, 1 special and 2 capital letters" class=""/>
			<Input type="password" placeholder="Repeat password" title="Repeat password" class=""/>		
		</Form>
		<Footer text="Already have an account?"
			text_link="Sign In"
			@click-on-link="$emit('sign_in')"
		/>
	</div>
</template>

<script>
import Form from '@/components/Molecules/Form.vue'
import Input from '@/components/Atoms/Input.vue'
import Title from '@/components/Atoms/Title.vue'
import Footer from '@/components/Atoms/Footer.vue'

export default {
	name: 'SignUp',
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