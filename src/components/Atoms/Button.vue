<template>
  <button class="btn" :class="{'btn_dark': dark, 'btn_disable': disable, 'btn_max-form': max_form}">
	{{text}}
  </button>
</template>

<script>
export default {
  name: 'Button',
  props: {
    text: String,
	dark: Boolean,
	disable: Boolean,
	max_form: Boolean
  }
}
</script>

<style scoped lang="scss">
.btn {
	display: flex;
	align-items: center;
	justify-content: center;
	min-width: 120px;
	height: 48px;
	padding: 14px;
	border-radius: 50px;
	border: none;
	font-family: 'Inter', sans-serif;
	font-style: normal;
	font-weight: 500;
	font-size: 14px;
	line-height: 20px;
	color: #000;
	background-color: #fff;
	cursor: pointer;

	&_disable {
		opacity: 0.4;
	}
	&_dark {
		color: #fff;
		background-color: #1E1A3E;
	}
	&_max-form {
		width: 100%;
	}
}
</style>
