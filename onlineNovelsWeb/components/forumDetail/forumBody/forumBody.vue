<template>
	<view class="forum-body">
		<view class="layui-tab">
			<ul class="layui-tab-title">
				<li class="lay-this">全部</li>
				<li>精华</li>
			</ul>
			<view class="layui-tab-content">
				<view class="layui-tab-item layui-show">
					<view class="post-order">
						<view class="order-title">排序</view>
						<view class="ck">
							<label class="comment-order-lab">
								<i class="material-icons">回复</i>
							</label>
						</view>
						<view class="ck">
							<label class="comment-order-lab">
								<i class="material-icons">发布</i>
							</label>
						</view>
						<view class="search">
							<view class="s-box">
								<input type="text" placeholder="帖名/用户" class="search-input keyword"/>
								<view class="search-icon keyword-seach">
									<i class="iconfont icon-31sousuo"></i>
								</view>
							</view>
						</view>
					</view>
					<view class="post-all">
						<view style="display: contents;">
							<view class="post-box">
								<view class="lanren1">
									<span>
										<br>
										精
										<br>
									</span>
								</view>
								<view class="post-header">
									<view class="head-pic-box">
										<image class="head-pic" src="@/static/photos/linmeng.jpg"></image>
									</view>
									<view class="head-info-box">
										<view class="user-name">Lin_9</view>
										<view class="user-lev">lv4</view>
										<br>
										<view class="time">3月前</view>
									</view>
								</view>
								<view class="post-body">
									<span class="post-tag">杂谈</span>
									<span class="post-content">
										<b>每日任务专用水楼</b>
										<br>
										<view class="content-text">
											<p>（感觉这里需要，我就把别处的水贴copy过来了）</p>
											<p>同时也为了保证论坛整洁</p>
											<p><br></p>
											<p> 每天登陆即可享有10经验值，每水一个贴就有1经验值哦~ 点赞也能获得经验哦~ 💕不用一个星期就能看小说了哦💕</p>
											<p><br></p>
											<p>在这里，你可以完成每天10个回复的任务💕</p>
											<p><br></p>
											<p>此处不作任何封禁处罚💕，顺便还可以给别人点赞同时完成每天10个点赞任务💕，被点赞也是随缘~</p>
											<p>加上自动签到每天打底30金币积分就到手了💕。</p>
											<p>每日也可以在祈愿池祈愿金币哦💕</p>
										</view>
									</span>
								</view>
								<view class="post-footer">
									<i class="iconfont icon-pinglun">评论(30313)</i>
									<i class="iconfont icon-yueduliang">阅读(17041)</i>
								</view>
								<view style="clear: both;"></view>
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"forumBody",
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">				
	.forum-body{
		border-radius: 20px 20px 0 0;
		// z-index: 1;
		position: relative;
		bottom: 25px;
		background-color: #ecf0f5;
		.layui-tab{
			margin: 10px 0;
			text-align: left;
		}
	}
	.layui-tab-title{
		margin-bottom: 0;
		position: relative;
		left: 0;
	    height: 40px;
	    white-space: nowrap;
	    font-size: 0;
	    border-bottom-width: 1px;
	    border-bottom-style: solid;
	    transition: all .2s;
		border-color: #e6e6e6;
		li{
			display: inline-block;
			vertical-align: middle;
			font-size: 14px;
			transition: all .2s;
			position: relative;
			line-height: 40px;
			min-width: 65px;
			padding: 0 15px;
			text-align: center;
			cursor: pointer;
		}
		.lay-this{
			color:#009688;
			&::after{
				pointer-events: none;
				border: none;
				border-bottom: 2px solid #5FB878;
				border-radius: 0;
				position: absolute;
				left: 0;
				top: 0;
				content: '';
				width: 100%;
				height: 41px;
				box-sizing: border-box;
			}
		}
	}
	.layui-tab-content{
		padding: 0;
		.layui-tab-item{
			display: none;
		}
		.layui-show{
			display: block;
		}
		.post-order{
			@media screen and (max-width: 960px){
			    grid-template-columns: 30px 50px 50px auto;
			    padding-top: 0.5em;
			    padding-bottom: 0.5em;
			    padding-left: 0.5rem;
			}
			display: grid;
			grid-template-columns: 4em 4em 4em auto;
			padding: 1em;
			background-color: #ffffff;
			.order-title{
				@media screen and (max-width: 960px){
					padding: 0px;
					margin: 0px;
				}
			    line-height: 40px;
			    margin-left: 5px;
			    color: #6a738f;
			    font-weight: 800;	
			}
		}
	}
	.ck{
		display: flex;
		justify-content: center;
		margin: auto;
		margin-top: 0.7rem;
		label{
			cursor: pointer;
		    position: relative;
		    display: flex;
		    justify-content: center;
		    align-items: center;
		    border-radius: 1rem;
		    width: 3em;
		    height: 2.8rem;
			box-shadow: 
				0.3rem 0.3rem 0.6rem #c8d0e7,
				-0.2rem -0.2rem 0.5rem white;
			i{
			    font-size: 1rem;
			    font-weight: 700;
				transition: 0.3s ease;
				color: #9baacf;
			}
		}
	}
	.search{
		display: flex;
		justify-content: flex-end;
		.s-box{
			width: 17rem;
		    height: 4rem;
		    position: relative;
			.search-input{
				@media screen and (max-width: 960px){
					width: 7rem;
				    margin-left: 2rem;
				}
				outline: 0;
				width: 10rem;
			    height: 4rem;
			    border: none;
			    border-radius: 1rem;
			    font-size: 1.4rem;
			    padding-left: 1rem;
			    padding-right: 3em;
				color: #9baacf;
				box-shadow: 
					inset 0.2rem 0.2rem 0.5rem #c8d0e7, 
					inset -0.2rem -0.2rem 0.5rem white;
			}
		}
	}
		
	.search-icon{			
		@media screen and (max-width: 960px){
			padding: 0.5rem 4rem;
		}
		height: 2rem;
	    position: absolute;
	    font-size: 2rem;
	    padding: 0.5rem 3rem;
	    display: flex;
		transition: 0.3s ease;
		right: 0;
		top: 0.5em;
		cursor: pointer;
		color:#9baacf;
	}
	ul{
		margin-top: 0;
		padding: 0;
	}
	label{
		max-width: 100%;
		margin-bottom: 5px;
		font-weight: 700;
	}
	.post-box{
		// width: 100%;
		min-height: 100px;
		background-color: white;
		margin-bottom: 10px;
		padding: 8px;
		box-shadow: 5px 10px 10px 1px #03032b1c;
		position: relative;
		.lanren1{
		    display: block;
		    width: 2em;
		    height: 2em;
		    line-height: 0.72em;
		    background: #ff47ab;
			transform: rotate(-22.5deg);
			position: absolute;
			top: 2em;
			right: 5%;
			text-align: center;
			text-decoration: none;
			color: #fff;
			font-weight: bold;
			transition: transform 0.3s ease;
			span{
			    display: block;
			    width: 2em;
			    height: 2em;
			    background: #ff47ab;
			    transform: rotate(45deg);
			}
		}
		.post-header{
			width: 100%;
		    height: 31px;		
			.head-pic-box{
				margin-right: 5px;
				float: left;
				.head-pic{
					height: 31px;
					width: 31px;
					border-radius: 50%;
					margin: auto;
				}
			}
			.head-info-box{
				width: calc(100% - 35px);
				height: 31px;
				font-size: 10px;
			}
		}
	}
	.user-name{
		margin-right: 5px;
	    font-weight: bolder;
	    color: #3D9EEA;
		display: inline-block;
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
	.time{
		margin-left: 5px;
	}
	.post-body{
		width: 100%;
	    min-height: 40px;
	    margin-top: 5px;
	    max-height: 300px;
	    overflow: hidden;
	    white-space: normal;
	    text-overflow: ellipsis;
	    padding: 8px;
	    cursor: pointer;
	}
	.post-tag{
		width: 40px;
	    height: 20px;
	    padding: 2px;
	    border-radius: 5px;
	    border: 0.5px solid #87CEFF;
	    color: #87CEFF;
	    margin-right: 5px;
	    font-size: 10px;
		transform: scale(0.8);
	    display: inline-block;
	    text-align: center;
	    line-height: 16px;
	}
	.post-footer{
		width: 100%;
	    height: 20px;
	    font-size: 12px;
	    color: #006d90;
	    line-height: 20px;
	    margin-top: 5px;
	    padding: 5px;
		i{
			float: right;
			margin-right: 10px;
			font-size: 13px;
		}
	}
</style>