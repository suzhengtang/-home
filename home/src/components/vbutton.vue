<template>
	<div>
		<button :class="type" @click="$emit('abc')" ><slot></slot></button>
	</div>
</template>
<style lang="less">
	@import "../../static/less/index";
		button {
			.w(347);
			.h(44);
			border-radius: 44px;
			.fs(16);
			outline: none;
			border: none;
		}
		.primary {
			background-color: #33b4ff;
			color: #fff;
			.mt(20);
		}
		.default {
			.mt(20);
			color: #33b4ff;
			border: 1px solid #33b4ff;
			background-color: #fff;
		}
		.out{
			color: #888;
			border: 1px solid #ccc;
			background-color: #fff;
		}
</style>
<script type="text/javascript">
	export default {
		data() {
			return {}
		},
		computed: {},
		props: {
			type:{
				type:String,
				default:'default'
			}
		},
		methods: {},
		components: {}
	}
</script>
