<template>
  <div id="app">
	<Enter v-if="screen === 'enter'"
		@sign_up="screen = 'sign_up'"
		@sign_in="screen = 'sign_in'"
	/>
	<SignUp v-if="screen==='sign_up'"
		@sign_in="screen = 'sign_in'"
		@register="screen = 'main'"
	/>
	<SignIn v-if="screen==='sign_in'"
		@sign_up="screen = 'sign_up'"
		@login="screen = 'main'"
	/>
	<Main v-if="screen==='main'" :username="username" />
  </div>
</template>

<script>
import Enter from './components/Pages/Enter.vue'
import SignUp from './components/Pages/SignUp.vue'
import SignIn from './components/Pages/SignIn.vue'
import Main from './components/Pages/Main.vue'

export default {
  name: 'App',
  components: {
	Enter,
	SignUp,
	SignIn,
	Main
  },
  data() {
	return {
		screen: 'enter', // enter, sign_in, sign_up, main
		username: 'John Doe'
	}
  }
}
</script>

<style lang="scss">
body {
	margin: 0;
}
#app {
	position: relative;
	box-sizing: border-box;
	// padding-top: 63px;
	padding: 63px 14px 0;

	height: 100vh;
	// padding: 0 14px;
	font-family: 'Inter', sans-serif;
	font-style: normal;
	font-weight: normal;
	font-size: 14px;
	text-align: center;
	color: #181C43;
	background-color: #FAF3F3;
}
// .screen {
// 	position: relative;
// 	height: 100%;
// 	box-sizing: border-box;
// 	padding-top: 63px;
// }
</style>
