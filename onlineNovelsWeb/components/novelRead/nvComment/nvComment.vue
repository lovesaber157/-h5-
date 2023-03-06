<template>
	<view class="box" id="novel-comment-list">
		<view class="box-body">	
			<view class="comment-list">
				<view class="h3">
					评论(共71条)
					<button id="comment-btn" class="btn btn-primary" style="padding: 4px 26px; font-size: 13px; float: right; margin-right: 10px; border-radius: 3px; border-color: rgb(20, 185, 200); background: rgb(20, 185, 200);">发表评论</button>
				</view>
				<hr>
				<view class="comment  hot-comment ">
					<view class="left-box">
						<view class="imgdiv user-info-show">
							<image class="imgCss" src="@/static/photos/storeimg04.jpg"></image>
						</view>
						<view class="thumbs-up do-thumbs-up">
							<i class="iconfont icon-dianzan">(54)</i>
						</view>
					</view>
					<view class="comment-details">
						<view class="comment-title">
							<span class="comment-name">kdhr单推人</span>
							<span class="c-floor">1楼</span>
							<span class="time">2月前</span>
						</view>
						<view class="del">
							<span class="show-reply-list">查看剩余1条回复</span>
							<i class="iconfont icon-paixu1" style="margin-right: 20px;">举报</i>
						</view>
						<view class="comment-content">
							<p>题材好像很有趣的样子</p>
						</view>
						<view style="width: 100%;">
							<i style="float: right; margin-right: 20px; margin-bottom: 8px;" class="iconfont icon-pinglun">回复</i>
						</view>
						<view class="replay-list">
							<view class="replay">
								<view class="simgdiv user-info-show">
									<image class="simg" src="@/static/photos/linmeng.jpg"></image>
								</view>
								<view class="reply-box">
									<view class="reply-name">
										<b style="font-weight: 700;">雪风智乃：</b>
									</view>
									<view class="reply-btn-box">
										<i class="iconfont icon-paixu">举报</i>
										<i class="iconfont icon-pinglun" style="margin-left: 40px;">回复</i>
									</view>
									<span class="reply-content">
										<p>是，BS吗？</p>
									</span>
								</view>
								<span class="time reply-time">2月前</span>
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		<view class="box-footer comment-box"></view>
		<view style="clear: both;"></view>
	</view>
</template>

<script>
	export default {
		name:"nvComment",
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	#novel-comment-list{
		overflow: visible;
	}
	.box{
		@media (max-width:960px) {
			width: 100%;
		}
		background: #ffffff;
		position: relative;
	    border-radius: 3px;
	    border-top: 0px solid #d2d6de;
	    margin-bottom: 20px;
	    width: 80%;
	    margin: auto;
	    overflow: hidden;
		.box-body{
			border-top-left-radius: 0;
			border-top-right-radius: 0;
			border-bottom-right-radius: 3px;
			border-bottom-left-radius: 3px;
			padding: 10px;
			.comment-list{
				background-color: #ffffff;
				padding-top: 5px;
				padding-left: 5px;
				width: 100%;
				margin: 0 auto;
				.comment{
					width: 100%;
					margin-top: 10px;
				}
			}
		}
		.comment-box{
			display: none;
		}
		.box-footer{
			background: none;
			border-top: 0.5px solid #939393;
			border-top-left-radius: 0;
			border-top-right-radius: 0;
			border-bottom-right-radius: 3px;
			border-bottom-left-radius: 3px;
			padding: 10px
		}
	}
	hr{
		margin-top: 20px;
		margin-bottom: 20px;
		border: 0;
		border-top: 1px solid #eee;
	}
	.h3{
		font-size: 24px;
		margin-top: 20px;
		margin-bottom: 10px;
		font-weight: 500;
		line-height: 1.1;
		.btn{
			border: 1px solid transparent;
			display: inline-block;
			margin-bottom: 0;
			line-height: 1.42857143;
			text-align: center;
			white-space: nowrap;
			vertical-align: middle;
			font-weight: 400;
			touch-action: manipulation;
			cursor: pointer;
			user-select: none;
		}
		.btn-primary{
			color: #fff;
		}
	}
	.left-box{
		float: left;
		display: grid;
		width: 60px;
		grid-template-rows: 70% auto;
		.imgdiv{
			width: 60px;
			height: 60px;
			float: left;
			position: relative;
			.imgCss{
				width: 50px;
				height: 50px;
				border-radius: 50%;
				vertical-align: middle;
			}
		}
		.user-info-show{
			cursor: pointer;
		}
		.thumbs-up{
			font-size: 10px;
		    transform: scale(0.8);
		    margin-top: 5px;
		    cursor: pointer;
		    width: 50px;
		    display: inline-block;
		    text-align: center;
		}
	}
	.comment-details{
		float: left;
		width: calc(100% - 60px);
		.comment-title{
			display: flex;
			align-items: center;
			float: left;
			span{
				margin-left: 10px;
			}
			.comment-name{
				color: #3F9EEA;
				font-size: 16px;
				font-weight: bolder;
			}
		}
	}
	.del{
		float: right;
	}
	.comment-content{
		clear: both;
		margin: 5px 45px 5px 10px;
		font-size: 14px;
		overflow: hidden;
	}
	p{
		margin: 0 0 10px;
	}
	.show-reply-list{
		margin-right: 45px;
		color: blue;
		cursor: pointer;
	}
	.replay-list{
		clear: both;
		// display: none;
		width: 100%;
		padding-right: 15px;
		margin-top: 10px;
		font-size: 13px;
		.replay{
			clear: both;
			width: 90%;
			margin: 4 auto;
			.reply-box{
				display: inline-block;
				float: left;
				width: calc(100% - 35px);
				margin-top: 5px;
				min-height: 50px;
				line-height: 30px;
				margin-left: 5px;
				overflow: hidden;
			}
		}
	}
	.simg{
		width: 30px;
		height: 30px;
		border-radius: 50%;
		vertical-align: middle;
	}
	.reply-name{
		color: #3D9EEA !important;
		display: inline-block !important;
		float: left !important;
	}
	.reply-btn-box{
		float: right;
		text-align: right;
	}
	.reply-content{
		display: inline-block;
	}
	.reply-time{
		float: right;
		font-size: 11px;
		margin-bottom: 5px;
	}
	.simgdiv{
		width: 30px;
		height: 30px;
		float: left;
		display: inline-block;
		position: relative;
		cursor: pointer;
	}
</style>