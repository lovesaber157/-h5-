<template>
	<view id="center-body">
		<view class="layui-tab">
			<ul class="layui-tab-title">
				<li class="layui-this">帖子</li>
				<li>关注</li>
				<li>粉丝</li>
				<li>资历</li>
			</ul>
			<view class="layui-tab-content">
				<view class="layui-tab-item layui-show">
					<view class="post-all">
						<view class="load-more" style="display: none;">点击加载更多</view>
						<view class="loading" style="display: none;">
							<image class="loading-img" src="@/static/photos/load.gif">加载中...</image>
						</view>
						<view class="no-more">
							已经没有更多了
						</view>
					</view>
				</view>
				<view class="layui-tab-item"></view>
				<view class="layui-tab-item"></view>
				<view class="layui-tab-item">
					<view class="zl-grid"></view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"centerBody",
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	.layui-tab{
		margin: 0;
		text-align: left;
		.layui-tab-title{
			padding: 0;
			position: relative;
		    left: 0;
		    height: 40px;
		    white-space: nowrap;
		    font-size: 0px;
		    border-bottom-width: 1px;
		    border-bottom-style: solid;
			margin-bottom: 0px;
		    margin-top: 0px;
		    background-color: #fffdfd;
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
			.layui-this{
				&::after{
					box-sizing: border-box;
					pointer-events: none;
				    position: absolute;
				    left: 0;
				    top: 0;
				    content: '';
				    width: 100%;
				    height: 41px;
				    border-bottom: 2px solid #5FB878;
				}
				color: #009688;
			}
		}
		.layui-tab-content{
			padding: 0;
			.layui-tab-items{
				display: none;
				.zl-grid{
					display: grid;
				    grid-template-columns: 50% 50%;
				}
			}
			.layui-show{
				display: block;
			}
		}
	}
	.load-more{
	    box-shadow: 5px 10px 10px 1px #03032b1c;
	    border-radius: 5px;
	    border: 0px;
	    background-color: #F2F2F2;
	    width: 100%;
	    height: 30px;
	    padding: 10px;
	    text-align: center;
	    font-size: 15px;
	    line-height: 11px;
	    color: #696969;
	    cursor: pointer;
	}
	.loading{
		width: 100%;
	    height: 40px;
	    padding: 10px;
	    text-align: center;
	    font-size: 15px;
	    color: #696969;
		.loading-img{
			width: 15px;
		    height: 15px;
		    margin-right: 5px;
		    margin-bottom: 3px;
		}
	}
	.no-more{
		background-color: #F2F2F2;
		width: 100%;
		height: 40px;
		padding: 10px;
		text-align: center;
		font-size: 15px;
		line-height: 11px;
		color: #696969;
		cursor: pointer;
		display: none;
	}
</style>