<template>
	<view id="app">
		<section class="content-header">
			<view id="h1">论坛及帖子收藏<small></small></view>
		</section>
		<section class="content">
			<view class="row">
				<view class="col-12">
					<view class="layui-tab">
						<ul class="layui-tab-title">
							<li class="layui-this" @click="changeShow(0)">论坛</li>
							<li @click="changeShow(1)">帖子</li>
						</ul>
						<view class="layui-tab-content">
							<view class="layui-tab-item" v-show="isShow" style="padding-top: 10px;">
								<view class="forum-box">
									<ul class="forum-left-list">
										<span>
											<li class="forum-li">
												<image class="logo-img" src="@/static/photos/other-220213234448-nf59.jpg">沒有信徒的女神大人</image>
											</li>
										</span>
									</ul>
									<ul class="forum-right-list">
										<span>
											<li class="forum-li">
												<image class="logo-img" src="@/static/photos/other-220213234448-nf59.jpg">沒有信徒的女神大人</image>
											</li>
										</span>
									</ul>
								</view>
							</view>
							<view class="layui-tab-item" v-show="!isShow"  style="padding-top: 10px;">
								<view class="post-box">
									<view class="post-header">
										<view class="post-pic-box">
											<image class="head-pic" src="@/static/photos/sora.jpg"></image>
										</view>
										<view class="head-info-box">
											<span class="user-name">帕</span>
											<span class="user-lev">lv6</span>
											<br>
											<span class="time" style="margin-left: 5px;">1年前</span>
										</view>
									</view>
									<view class="post-body">
										<view class="post-tag">杂谈</view>
										<view class="post-content">
											<b>经验价格怎么涨的飞起，是论坛新人越来越多了吗</b>
											<br>
											<span class="content-text">
												<p>都从十几二十几到现在最低快70一个（+3）经验了</p>
												<p>经验好像就主要是对新人比较有用，等级到LV4好像就没太大用了</p>
												<p>话说等级好像就权限有点差别吧，没发现别的福利</p>
												<br>
												<P>12/28</P>
												<p>日最低价格回落到30.4G了（计税后）  ，看样子虚高的泡沫基本上破灭了</p>
											</span>
										</view>
									</view>
									<view class="post-footer">
										<i class="iconfont icon-pinglun">评论(30313)</i>
										<i class="iconfont icon-yueduliang">阅读(17041)</i>
									</view>
									<view style="clear: both;"></view>
								</view>
								<view style="width: 100%;"></view>
							</view>
						</view>
					</view>
				</view>
			</view>
		</section>
	</view>
</template>

<script>
	export default {
		name:"forumCollection",
		data() {
			return {
				isShow:true
			};
		},
		methods:{
			changeShow(index){
				let liElement= document.getElementsByClassName('layui-tab-title')[0].children
				if(liElement[index].className!="layui-this"){
					let otherIndex=index?0:1
					liElement[index].className="layui-this"
					liElement[otherIndex].className=""
					this.isShow=!this.isShow
				}
			}
		}
	}
</script>

<style lang="scss">
	@import "@/static/scss/public.scss";
	.layui-tab{
		margin: 10px 0;
		text-align: left;
	}
	.layui-tab-title{
		border-color: #e6e6e6;
		margin-bottom: 0px;
	    position: relative;
	    left: 0;
	    height: 40px;
	    white-space: nowrap;
	    font-size: 0;
	    border-bottom-width: 1px;
	    border-bottom-style: solid;
		transition: all .2s;
		margin-top: 0;
		padding: 0;
		li{
			font-size: 14px;
			transition: all .2s;
			vertical-align: middle;
			display: inline-block;
			position: relative;
		    line-height: 40px;
		    min-width: 65px;
		    padding: 0 15px;
		    text-align: center;
		    cursor: pointer;
		}
		.layui-this{
			color: #009688;
			&::after{
				border-bottom: 2px solid #5FB878;
				position: absolute;
			    left: 0;
			    top: 0;
			    content: '';
			    width: 100%;
			    height: 41px;
				box-sizing: border-box;
			    pointer-events: none;
			}
		}
	}
	.layui-tab-item{
		// display: none;
	}
	.layui-show{
		display: block;
	}
	.forum-box{
	    width: 100%;
	    padding: 5px;
		ul{
		    list-style-type: none;
		    padding: 10px;
			li{
				background-repeat: no-repeat;
			    background-position: 0px 5px;
			    height: 50px;
			    line-height: 50px;
			    cursor: pointer;
			    text-align: center;
			    background-color: white;
			    border-radius: 5px;
			    margin-top: 10px;
			    overflow: hidden;
			    white-space: nowrap;
			    text-overflow: ellipsis;
			}
		}
		.forum-left-list {
		    float: left;
		    width: 49%;
			padding: 0;
		}
		.forum-right-list{
			float: right;
			width: 49%;
			padding: 0;
		}
	}
	.logo-img{
	    width: 40px;
	    height: 40px;
	    border-radius: 10px;
	    float: left;
	    margin: 5px;
	}
	.post-box{
		width: 100%;
	    min-height: 100px;
	    background-color: white;
	    margin-bottom: 10px;
	    padding: 10px;
	    box-shadow: 5px 10px 10px 1px #03032b1c;
	    position: relative;
		.post-header{
			width: 100%;
		    height: 31px;
			.post-pic-box{
				margin-right: 5px;
				float: left;
				.head-pic{
					height: 31px;
				    width: 31px;
				    border-radius: 50%;
				    margin: auto;
				}
			}
		}
	}
	.head-info-box {
	    width: calc(100% - 35px);
	    height: 31px;
	    font-size: 10px;
		.user-name{
			margin-right: 5px;
		    font-weight: bolder;
		    color: #3D9EEA;
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
		}
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
		.post-tag{
			width: 40px;
		    height: 20px;
		    padding: 2px;
		    border-radius: 5px;
		    border: 0.5px solid #87CEFF;
		    color: #87CEFF;
		    margin-right: 5px;
		    font-size: 10px;
		    -webkit-transform: scale(0.8);
		    display: inline-block;
		    text-align: center;
		    line-height: 16px;
		}
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
		}
	}
</style>