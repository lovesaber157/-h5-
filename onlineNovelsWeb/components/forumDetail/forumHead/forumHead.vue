<template>
	<view class="forum-head">
		<view class="forum-background"/>
		<view class="cover">
			<span>
				<image class="forum-image" src="@/static/photos/other-210519183821-BenC.jpg"></image>
			</span>
		</view>
		<view class="forum-head-box">
			<view class="top-area">
				<span class="forum-title">《香格里拉》</span>
			</view>
			<view class="middle-area">
				<span class="follow-info">1288关注	48帖子 41672阅读</span>
				<text class="follow-btn">+ 关注</text>
				<text class="unfollow-btn" style="display: none;">已关注</text>
				<text class="n-btn btn-share">分享</text>
			</view>
			<view class="footer-area">
				<view class="sticky">
					<view class="top-group-view">
						<text class="top-post">置顶</text>
						<text class="top-tips">每日任务专用水楼</text>
						<text class="top-post">置顶</text>
						<text class="top-tips">台版電子書附錄：加筆外傳小說</text>
						<text class="top-post">置顶</text>
						<text class="top-tips">台版電子書第3集附錄：加筆外傳小說</text>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"forumHead",
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">	
	.forum-background{
		@media screen and(max-width:960px){
			height: 100px;
			background-size: cover;
		}
		background-image: url("@/static/photos/sora.jpg");
		width: 100%;
		height: 150px;
	}
	.cover{
		@media screen and (max-width:960px){
			width: 80px;
			height: 120px;
			top:40px;
			left: 40px;
		}
		width: 90px;
		height: 120px;
		position: absolute;
		top: 60px;
		left: 100px;
		.forum-image{
			height: 100%;
			width: 100%;
		}
	}
	.forum-head-box{
		width: 100%;
		height: 220px;
		background-color: #02134a;
		.top-area{
			width: 100%;
			height: 60px;
			.forum-title{
				display: inline-block;
				float: right;
				width: 100%;
				height: 60px;
			    color: white;
			    overflow: hidden;
			    white-space: normal;
			    text-overflow: ellipsis;
			    font-size: 16px;
			    font-weight: 600;
			    padding-top: 10px;
			    margin-right: 10px;
			    text-align: center;
			}
		}
		.middle-area{
			height: 30px;
			width: 100%;
			line-height: 30px;
			.follow-info{
				@media screen and(max-width:960px){
				    margin-left: 15px;
				    margin-top: 5px;
				}
			    display: inline-block;
			    font-size: 10px;
			    color: white;
			    float: left;
			    margin-left: 80px;
			}
			.follow-btn,.unfollow-btn{
				@media screen and (max-width: 960px){
					margin-right: 30px;
				}
				display: inline-block;
				float: right;
				width: 50px;
				height: 25px;
				color: white;
				margin-right: 100px;
			    margin-top: 5px;
			    text-align: center;
			    background-color: #add8e645;
			    line-height: 25px;
			    border-radius: 5px;
			    font-size: 10px;
			    cursor: pointer;
			}
			.btn-share{
				font-size: 12px;
			}
			.n-btn{
				text-align: center;
			    background-color: #add8e645;
			    line-height: 25px;
			    border-radius: 5px;
				cursor: pointer;
				margin: 10px;
				display: inline-block;
				float: right;
				width: 50px;
				height: 25px;
				color: white;
				margin-top: 5px;
			}
		}
		.footer-area{
			width: 100%;
			height: 90px;
			.sticky{
			    color: white;
			    font-size: 14px;
			    background-color: #07215694;
			    margin-top: 20px;
			    // margin-left: 15px;
			    height: 70px;
			    padding: 10px;
			    width: calc(100% - 30px);
				.top-group-view{
					width: 100%;
					height: 20px;
					.top-post{
						color: #CD4F39;
					    margin-right: 10px;
					    height: 100%;
					    display: inline-block;
					    vertical-align: middle;
					}
					.top-tips{
					    white-space: nowrap;
					    text-overflow: ellipsis;
					    width: calc(100% - 40px);
					    display: inline-block;
					    height: 100%;
					    vertical-align: middle;
					    cursor: pointer;
					}
				}
			}
		}
	}
</style>