<template>
	<div id="my">
		<!--顶部导航栏-->
		<regist-title title="个人中心" address=""></regist-title>

		<!--内容部分-->
		<div class="my-all">
			<h4>诺漫斯账号</h4>
			<div class="my-title">
				<div class="my-name">
					<div class="name-left">
						<img src="../../assets/logo.png" alt="">
					</div>
					<div class="name-right">
						<h5>苏正堂</h5>
						<p>1037617576</p>
					</div>
				</div>
				<div class="my-name-top">
					安全等级 <span>80</span>分 存在<span>1</span>项风险
				</div>
			</div>
			<p class="title">基本资料</p>
			<div class="my-title">
				<ul>
					<li>账号密码</li>
					<li>安全邮箱</li>
					<li>安全手机</li>
					<li>保密问题</li>
				</ul>
			</div>
			<p class="title">推荐使用</p>
			<div class="my-title">
				<ul>
					<li>小米安全令牌</li>
				</ul>
			</div>
			<p class="title">其他</p>
			<div class="my-title">
				<ul>
					<li>修改个人资料</li>
					<li>绑定授权</li>
				</ul>
			</div>

			<!--退出按钮-->
			<div class="outBtn">
				<router-link to="../login"><vbutton type="out">退出</vbutton></router-link>
			</div>
		</div>
	</div>
</template>
<style lang="less" scoped>
	@import "../../../static/less/index";

	.my-all {
		width: 100%;
		height: 100%;
		background-color: #f6f6f6;
		h4 {
			.fs(24);
			font-weight: 500;
			color: #ff6928;
			.padding(20, 14);
		}
		.my-title {
			width: 100%;
			background-color: #fff;
			border-top: 1px solid #eee;
			border-bottom: 1px solid #eee;
			.my-name {
				.w(347);
				border-bottom: 1px solid #eee;
				overflow: hidden;
				margin: 0 auto;
				.name-left {
					float: left;
					.padding(14, 0);
					img {
						.w(38);
						.h(38);
						/*border-radius: 50%;*/
						background-color: skyblue;
					}
				}
				.name-right {
					float: left;
					.margin(12, 10);
					h5 {
						.fs(16);
						color: #333;
					}
					p {
						color: #aaa;
					}
				}
			}
			.my-name-top {
				.padding(20, 14);
				.fs(16);
				color: #aaa;
				span {
					color: #ff6b2b;
				}
			}
			ul{
				.w(347);
				margin: 0 auto;
				li{
					border-bottom: 1px solid #eee;
					.padding(20,0);
					.fs(16);
					font-weight: 600;
					color: #666;
				}
				li:last-child{
					border-bottom: none;
				}
			}
		}
		.title {
			.margin(14,14);
			color: #888;
		}
		.outBtn{
			.margin(40,14);
		}
	}
</style>
<script type="text/javascript">
	import axios from 'axios';
	import title from '../title';
	import vbutton from '../vbutton.vue'

	export default {
		data() {
			return {}
		},
		created(){
			axios.get('').then((data)=>{
				console.log(data);
			})
		},
		computed: {},
		props: {},
		methods: {},
		components: {
			'regist-title': title,
			vbutton
		}
	}

</script>
