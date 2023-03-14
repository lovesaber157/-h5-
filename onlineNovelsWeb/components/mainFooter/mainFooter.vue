<template>
	<footer class="main-footer">
		<view>
			<p>Copyright©2021 masiro.moe & masiro.me.All rights reserved.版权所有 盗用必究。本站拥有本站部分字体或素材的版权或使用授权，任何未经同意的盗用皆为侵权行为。</p>
			<p>本站发布内容如无特别声明则其一切权利归属于其发布者、创作者或各自的版权所有者。</p>
		</view>
	</footer>
</template>

<script>
	export default {
		name:"mainFooter",
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	@media (max-width:767px) {
		.main-footer{
			margin-left: 0 !important;
		}
	}
	.main-footer{
		border-top-color:1px soild #d2d6de;
		border-left:1px solid #d2d6de;
		text-align: center;
		background: #fff;
		padding: 15px;
		color:#444;
		transition: transform .3s ease-in-out,margin .3s ease-in-out;
		margin-left: 230px;
	}
	//适配两种屏幕 min-width:768px
	.wrapper.sidebar-collapse{
		@media (min-width:768px) {
			.main-footer{
				margin-left: 50px;
			}
		}
	}
</style>