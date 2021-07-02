<template>
  <h1 class="title">
	{{text}}
  </h1>
</template>

<script>
export default {
  name: 'Title',
  props: {
    text: String
  }
}
</script>

<style scoped lang="scss">
.title {
	margin: 0;
	padding-bottom: 20px;
	font-family: 'Inter', sans-serif;
	font-style: normal;
	font-weight: 800;
	font-size: 22px;
	line-height: 30px;
	text-align: center;
	letter-spacing: 0.02em;
	color: #181C43;
}
</style>
