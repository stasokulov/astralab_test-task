<template>
<footer class="footer">
	<p class="footer__text">{{text}}</p>
	<a class="footer__link" @click="$emit('click-on-link')">{{text_link}}</a>
</footer>
</template>

<script>
export default {
  name: 'Footer',
  props: {
    text: String,
	text_link: String
  }
}
</script>

<style scoped lang="scss">
.footer {
	font-family: 'Inter', sans-serif;
	font-style: normal;
	font-weight: 500;
	font-size: 14px;
	line-height: 20px;
	text-align: center;
	color: #1E1A3E;
	&__text {
		margin: 0;
	}
	&__link {
		text-decoration: underline;
		cursor: pointer;
	}
}
</style>
