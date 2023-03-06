<template>
	<view id="center-head">
		<view class="forum-head-box">
			<view class="bg">
				<view class="head-area">
					<view class="avatar-box">
						<image class="avatar" src="@/static/photos/other-220315104645-DNdv.jpg"></image>
					</view>
					<view class="user-name-box">
						<text class="user-name-info">NPC001</text>
						<text class="user-lev">lv4</text>
					</view>
				</view>
				<view class="middle-area">
					<small>金币:947 经验值:1069/2000 粉丝:0  帖子:0 资历:356天</small>
					<small>ID:112481</small>
				</view>
				<view class="footer-area">
					
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"centerHead",
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	.forum-head-box{
		width: 100%;
		background-color: #02134a;
		height: 250px;
		.bg{
		    width: 100%;
		    height: inherit;
		    background-repeat: no-repeat;
		    background-position: center;
		    background-size: cover;
		    display: flex;
		    flex-direction: column;
		    align-items: center;
			.head-area{
				width: 100%;
				text-align: center;
				height: 145px;
				
			}
		}
	}
	.avatar-box{
		width: 100%;
		height: 120px;
		.avatar{
			height: 90px;
		    width: 90px;
		    border: 3px solid;
		    border-color: rgba(255,255,255,0.2);
		    border-radius: 50%;
		    margin-top: 15px;
		}
	}
	.user-name-box{
	    font-size: 15px;
	    font-weight: 600;
	    color: white;
	    width: 100%;
		.user-lev{
			display: inline-block;
		    width: 30px;
		    height: 13px;
		    border-radius: 10px;
		    background-color: #002a80;
		    color: white;
		    text-align: center;
		    line-height: 13px;
		}
	}
	.middle-area{
	    height: 60px!important;
	    text-align: center;
	    color: white;
	    display: flex;
	    flex-direction: column;
	    margin-bottom: 10px;
		width: 100%;
		line-height: 30px;
	}
	.footer-area{
		@media screen and(max-width:960px){
			width: 80%;
		}
		width: 100%;
		height: 25px;
		display: flex;
		justify-content: space-evenly;
	}
</style>