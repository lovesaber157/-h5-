<template>
	<ul class="dropdown-menu">
		<li class="user-header">
			<image class="user-image" src="@/static/photos/other-220315104645-DNdv.jpg"></image>
			<p>
				NPC001
				<text class="user-lev">lv4</text>
				<view style="font-size: 12px;">
					金币:957 粉丝:0
					<br>
					ID:112481
				</view>
			</p>
		</li>
		<li class="user-footer">
			<view class="pull-left">
				<text class="btn">设置</text>
			</view>
			<view class="pull-right">
				<text class="btn" @click="logout()">登出</text>
			</view>
			<view style="clear:both"></view>
		</li>
	</ul>
</template>

<script>
	export default {
		name:"dropdownMenu",
		data() {
			return {
				
			};
		},
		methods:{
			logout(){
				uni.navigateTo({
					url:"/pages/login/login"
				})
			}
		}
	}
</script>

<style lang="scss">
	.dropdown-menu{
		@media (max-width:991px) {
		    right: 5%;
		    border: 1px solid #ddd;
		    background: #fff;
		}
		border-bottom-right-radius: 4px;
		border-bottom-left-radius: 4px;
		right: 0;
		left: auto;
		border-top-right-radius: 0;
		border-top-left-radius: 0;
		padding: 1px 0 0 0;
		width: 280px;
		box-shadow: none;
		// top: 100%;
		// margin-top: 0;
		float: left;
		min-width: 160px;
	    margin: 2px 0 0;
	    font-size: 14px;
	    text-align: left;
	    list-style: none;
		.user-header{
			margin: 0;
		    height: 175px;
		    padding: 10px;
		    text-align: center;
			background: linear-gradient(45deg,#60eda0,#6febff, #9198e5);
			.user-image{
				height: 90px;
				width: 90px;
				border-radius: 50%;
				border: 3px solid rgba(255,255,255,0.2);
				cursor: pointer;
			}
			p{
				color: black;
				font-size: 17px;
				margin-top: 10px;
			}
			.user-lev{
			    display: inline-block;
			    width: 30px;
			    height: 13px;
			    border-radius: 10px;
			    background-color: #002a80;
			    color: white;
			    text-align: center;
			    line-height: 13px;
			    margin-left: 5px;
			    font-size: 10px;
			}
		}
		.user-footer{
		    background-color: #f9f9f9;
		    padding: 10px;
			.pull-left{
				float: left;
			}
			.pull-right{
				float: right;
			}
			.btn{
				&:hover{
					border-color: #adadad;
				}
				color: #666666;
				border-width: 1px;
				margin-bottom: 0;
			    font-size: 14px;
			    font-weight: 400;
			    line-height: 1.42857143;
			    text-align: center;
			    white-space: nowrap;
			    vertical-align: middle;
				display: inline-block;
				padding: 6px 12px;
				border: 1px solid #ddd;
			}
		}
	}
</style>