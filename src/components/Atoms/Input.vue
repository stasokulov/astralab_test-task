<template>
  <div class="field">
	<div class="field__header">
		<p class="field__title">{{title}}</p>
		<div v-if="prompt" class="prompt">
			<i class="prompt__icon"></i>
			<div class="prompt__text">{{prompt}}</div>
		</div>
	</div>
	<div class="field__content">
		<input class="field__input"
			:type="computedType"
			:placeholder="placeholder"
		>
		<i :class="{'field__eye-icon': type === 'password', 'field__eye-icon_close': computedTextIsHide, 'field__eye-icon_open': !computedTextIsHide }"
			@click="computedTextIsHide = !computedTextIsHide"
		></i>
	</div>
  </div>
</template>

<script>
export default {
  name: 'Input',
  props: {
    type: String,
	placeholder: String,
	title: String,
	prompt: {
		type: String,
		default: null
	},
	textIsHide: {
		type: Boolean,
		default: true
	}
  },
  data() {
	return {
		localTextIsHide: null
	}
  },
  computed: {
	computedTextIsHide: {
		get: function() {
			let localTextIsHide;
			this.localTextIsHide === null ?
			localTextIsHide = this.textIsHide :
			localTextIsHide = this.localTextIsHide;
			return localTextIsHide;
		},
		set: function(value) {
			this.localTextIsHide = value;
		}
	},
	computedType: function() {
		let computedType;
		this.type !== 'password' ?
		computedType = this.type :
			(this.computedTextIsHide === true ?
			computedType = 'password' :
			computedType = 'text');
		return computedType;
	}
  }
}
</script>

<style scoped lang="scss">
.field {
	display: flex;
	flex-direction: column;
	align-items: flex-start;
	&:not(:last-child) {
		padding-bottom: 24px;
	}

	&__header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		width: 100%;
		box-sizing: border-box;
		padding: 4px 18px;
	}

	&__title {
		margin: 0;
		font-family: 'Inter', sans-serif;
		font-style: normal;
		font-weight: 600;
		font-size: 12px;
		line-height: 20px;
		color: rgba(0, 0, 0, 0.8);
	}

	&__content {
		position: relative;
		width: 100%;
	}

	&__input {
		position: relative;
		display: flex;
		align-items: center;
		width: 100%;
		height: 36px;
		box-sizing: border-box;
		padding-left: 18px;
		padding-right: 34px;
		font-family: 'Inter', sans-serif;
		font-style: normal;
		font-weight: normal;
		font-size: 14px;
		line-height: 20px;
		color: rgba(0, 0, 0, 0.8);
		border-radius: 50px;
		border: none;
		background: #F3F3FA;
	}

	&__eye-icon {
		content: '';
		position: absolute;
		top: 14px;
		right: 16px;
		width: 18px;
		height: 12px;
		background-position: center;
		background-repeat: no-repeat;
		background-size: contain;
		cursor: pointer;

		&_open {
			background-image: url("data:image/svg+xml,%3Csvg width='20' height='13' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M10.14.33A9.86 9.86 0 00.97 6.58a9.86 9.86 0 0018.34 0A9.86 9.86 0 0010.14.33zm0 10.42a4.17 4.17 0 110-8.34 4.17 4.17 0 010 8.34zm0-6.67a2.5 2.5 0 100 5 2.5 2.5 0 000-5z' fill='%23181C43'/%3E%3C/svg%3E");
		}

		&_close {
			background-image: url("data:image/svg+xml,%3Csvg width='20' height='16' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M10.1 3.4a4.2 4.2 0 014 5.4l2.6 2.5c1.1-1 2-2.3 2.6-3.7A9.9 9.9 0 007.1 1.8L9 3.6l1.2-.2zM2.4.6c-.3.4-.3.9 0 1.2L4 3.5a10 10 0 00-3 4 9.9 9.9 0 0012.7 5.7l2.3 2.2a.8.8 0 101.2-1.2L3.6.6a.8.8 0 00-1.2 0zm7.7 11.1a4.2 4.2 0 01-3.7-5.9l1.3 1.3v.5a2.5 2.5 0 003 2.4l1.2 1.3a4 4 0 01-1.8.4zm2.5-4.4c-.1-1.2-1-2-2.2-2.2l2.2 2.2z' fill='%23181C43'/%3E%3C/svg%3E");
		}
	}
}
.prompt {
	position: relative;

	&:hover &__text {
		display: block;
	}

	&__icon {
		display: block;
		width: 12px;
		height: 12px;
		background-image: url("data:image/svg+xml,%3Csvg width='12' height='12' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M6.1.2a5.8 5.8 0 100 11.6A5.8 5.8 0 006.2.2zM6 9.4a.7.7 0 110-1.5.7.7 0 010 1.5zm2-4.3c0 .2-.3.5-.8.8-.6.5-.6.6-.6 1H5.3c0-.3 0-.6.2-.9 0-.2.3-.4.6-.7.4-.3.8-.5.8-1 0-.4-.4-.6-.8-.6-.5 0-1 .2-1.5.4l-.5-1c1-.5 2.7-.8 3.6 0 .6.5.6 1.4.3 2z' fill='%231E1A3E'/%3E%3C/svg%3E");
		background-position: center;
		background-repeat: no-repeat;
		background-size: contain;
		opacity: 0.2;
		cursor: pointer;
	}

	&__text {
		display: none;
		position: absolute;
		bottom: 12px + 7px;
		right: -11px;
		width: 184px;
		padding: 7px 11px;
		background-color: #1E1A3E;
		box-shadow: 0px 5.44862px 13.6215px rgba(0, 0, 0, 0.1);
		border-radius: 8px;
		font-family: 'Inter', sans-serif;
		font-style: normal;
		font-weight: normal;
		font-size: 10px;
		line-height: 14px;
		text-align: center;
		letter-spacing: -0.4px;
		color: #F3F3F3;

		&:after {
			content: '';
			position: absolute;
			bottom: -8px;
			right: 12px;
			width: 0;
			height: 0;
			border-style: solid;
			border-color: transparent;
			border-width: 4px;
			border-top: solid 4px #1E1A3E;
		}
	}
}
</style>
