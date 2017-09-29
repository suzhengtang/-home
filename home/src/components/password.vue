<template>
	<div id="psd">
		<!--标题部分-->
		<regist-title address=""></regist-title>

		<!--内容部分-->
		<div class="psd-content">
			<h3>注册智能家居账号</h3>
			<p>你注册的手机号码为<span>13538343551</span></p>
			<p>请设置您的密码：</p>
			<input type="password" placeholder="请输入密码" v-model="psd">
			<input type="password" placeholder="请输入确认密码" v-model="psdAgain">
			<p>密码长度8~16位，数字、字母、字符至少包含两种</p>
		</div>

		<!--提交按钮-->
		<div class="psd-btn">
			<vbutton type="primary" @abc="toLink">提交</vbutton>
		</div>
	</div>
</template>
<style lang="less" scoped>
	@import "../../static/less/index";

	.psd-content {
		width: 100%;
		.padding(0, 14);
		h3 {
			text-align: center;
			.fs(20);
			color: #696969;
			.margin(30, 0);
			font-weight: 500;
		}
		p {
			color: #aaa;

			span {
				color: #fe7416;
			}
		}
		p:nth-of-type(2) {
			.margin(10, 0)
		}
		p:nth-of-type(3) {
			color: #666;
		}
		input {
			border: 1px solid #ccc;
			border-radius: 10px;
			.h(44);
			.w(347);
			.pl(10);
			box-sizing: border-box;
			.margin(8, 0)
		}
	}

	.psd-btn {
		width: 100%;
		.padding(0, 14);
		.mt(80);
	}
</style>
<script type="text/javascript">
	import title from './title.vue';
	import vbutton from './vbutton.vue'

	export default {
		data() {
			return {
				psd: '',
				psdAgain: '',
			}
		},
		computed: {},
		props: {},
		methods: {
			toLink() {
				var reg = /^(?![0-9]+$)(?![a-zA-Z]+$)(?![!@#$%^&*]+$)([0-9A-Za-z]|[!@#$%^&*0-9]|[!@#$%^&*A-Za-z]){8,16}$/
				if (this.psd == '' || this.psdAgain == '') {
					alert('密码不能为空')
				} else if (this.psd != this.psdAgain) {
					alert('两次输入的密码不一致，请重新输入')
				} else if (this.psd == this.psdAgain && this.psd.length <8) {
					alert('密码长度必须要大于等于8')
				} else if (this.psd == this.psdAgain && this.psd.length >16) {
					alert('密码长度必须要小于等于16')
				} else if (reg.test(this.psd) == true && reg.test(this.psdAgain) == true) {
					this.$router.push({path: './login'})
				}
			}
		},
		components: {
			'regist-title': title,
			vbutton
		}
	}
</script>
