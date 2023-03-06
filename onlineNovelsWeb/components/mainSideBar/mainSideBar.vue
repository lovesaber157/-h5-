<template>
	<view class="main-sidebar">
		<section class="sidebar">
			<view class="user-panel">
				<view class="pull-left image">
					<image class="user-image" src="@/static/photos/other-220315104645-DNdv.jpg"></image>
				</view>
				<view class="pull-left info">
					<p>
						NPC001
						<view class="user-lev">Lv4</view>
					</p>
					<p>
						<view class="user-info">金币:915 粉丝:0</view>
					</p>
				</view>
			</view>
			<ul class="sidebar-menu">
				<li class="header">菜单</li>
				<li v-for="item in sidebarMenu">
					<view @click="goToPage(item)">
						<span :class="item.iconClass"></span>
						<text>{{item.titleName}}</text>
						<span :class="[item.treeToshow?'iconfont icon-zhankai1 pull-right':'iconfont icon-houtui pull-right']" v-if="item.treeView" @click="changeShow(item)"></span>
					</view>
					<ul class="treeview-menu" v-if="item.treeToshow">
						<li v-for="treeItem in item.treeView">
							<view @click="goToPage(treeItem)">
								<span :class="treeItem.iconClass"></span>
								<text>{{treeItem.titleName}}</text>
							</view>
						</li>
					</ul>
				</li>
			</ul>
		</section>
	</view>
</template>

<script>
	export default {
		name:"mainSideBar",
		data() {
			return {
				sidebarMenu:[
					{
						titleName:"首页",
						iconClass:"iconfont icon-university-full",
						page:"/pages/index/index",
						treeToshow:false
					},
					{
						titleName:"公告",
						iconClass:"iconfont icon-huaban",
						page:"/pages/announcements/announcements",
						treeToshow:false
					},
					{
						titleName:"小说论坛",
						iconClass:"iconfont icon-shuben_2",
						treeView:[
							{
								titleName:"全部小说",
								iconClass:"iconfont icon-shuben_2",
								page:"/pages/novelList/novelList?classify=2",
							},
							{
								titleName:"日轻",
								iconClass:"iconfont icon-shuben_2",
								page:"/pages/novelList/novelList?classify=1",
							},
							{
								titleName:"原创",
								iconClass:"iconfont icon-gongchang",
								page:"/pages/novelList/novelList?classify=0",
							},
							{
								titleName:"小说论坛",
								iconClass:"iconfont icon-duihua",
								page:"/pages/forumList/forumList?type=1"
							},
							{
								titleName:"独立论坛",
								iconClass:"iconfont icon-kafei",
								page:"/pages/forumList/forumList?type=0"
							},
						],
						treeToshow:false
					},
					{
						titleName:"排行榜",
						iconClass:"iconfont icon-liebiao",
						treeToshow:false,
						treeView:[
							{
								titleName:"论坛排行",
								iconClass:"iconfont icon-liebiao",
								page:"/pages/leaderboard/leaderboard"
							}
						]
					},
					{
						titleName:"个人中心",
						iconClass:"iconfont icon-jurassic_user",
						treeToshow:false,
						page:"#",
						treeView:[
							{
								titleName:"个人主页",
								iconClass:"iconfont icon-liebiao",
								page:"/pages/personalCenter/personalCenter"
							},
							{
								titleName:"个人收藏",
								iconClass:"iconfont icon-liebiao",
								page:""
							},
							{
								titleName:"论坛收藏",
								iconClass:"iconfont icon-liebiao",
								page:"/pages/forumCollection/forumCollection"
							}
						]
					}
				]
			};
		},
		methods:{
			changeShow(element){
				element.treeToshow=!element.treeToshow
			},
			goToPage(element){
				uni.redirectTo({
					url:element.page
				})
			}
		},
	}
</script>

<style lang="scss">
	@media (max-width:768px) {
		.main-sidebar{
			//控制显影
			// transform: translate(0,0);
			transform: translate(-230px,0);
			width: 50px;
			padding-top: 100px;
		}
	}
	.main-sidebar{
		display: block;
		background-color: #f9fafc;
		transition: transform .3s ease-in-out,width .3s ease-in-out;
		position: absolute;
		top: 0;
		left: 0;
		padding-top: 50px;
		min-height: 100%;
		min-height: 100%;
		height: 100%;
		width: 230px;
		z-index: 200;
	}
	.sidebar{
		padding-bottom: 10px;
		.user-lev{
			font-size: 9px;
			transform: scale(0.8);
			display: inline-block;
			width: 30px;
			height: 13px;
			border-radius: 10px;
			background-color: #002a80;
			color: white;
			text-align: center;
			line-height: 13px;
		}
		.user-info{
			font-size: 9px;
			transform: scale(0.8);
		}
		a{
			color: #444;
		}
	}
	.main-sidebar .user-panel{
		overflow: hidden;
	}
	.user-panel{
		position: relative;
		width: 100%;
		padding: 10px;
	}
	.sidebar-menu{
		padding:0;
		white-space: nowrap;
		overflow: hidden;
		list-style: none;
		>li.header{
			color: #848484;
			background: #f9fafc;
			overflow: hidden;
			text-overflow: clip;
			white-space: nowrap;
		}
		>li{
			margin: 0;
			position: relative;
			transition: border-left-color .3s ease;
		}
		li.header{
			padding: 10px 25px;
			font-size: 12px;
		}
		>li>view{
			border-left: 3px solid transparent;
			font-weight: 600;
		}
		li>view{
			position: relative;
			padding: 12px 5px 12px 13px;
			display: block;
			text-decoration: none;
			.iconfont{
				width: 20px;
				// margin-left: -40px;
			}
			>.pull-right{
				position: absolute;
				right: 10px;
				top: 50%;
				margin-top: -10px;
			}
		}
		>li>.treeview-menu{
			background-color: #f4f4f5;
		}
		.treeview-menu{
			//控制显示
			// display: none;
			list-style: none;
			padding-left: 5px;
			>li>view{
				padding: 5px 5px 5px 15px;
				display: block;
				font-size: 14px;
				color: #777;
			}
			li>view{
				position: relative;
			}
		}
	}
	.pull-left{
		float: left;
		>.info{
			color: #444;
			padding: 5px 5px 5px 15px;
			line-height: 1;
			position: absolute;
			left: 55px;
			p{
				font-weight: 400;
				margin-bottom: 9px;
			}
		}
		.info{
			font-size: 10px;
		}
	}
	.image{
		image{
			max-width: 45px;
			max-height: 45px;
			border-radius: 50%;
			vertical-align: middle;
		}
	}
	li{
		list-style: none;
	}
	p{
		margin: 0 0 10px;
	}
	span{
		display: inline-block;
	}
	//适配两种屏幕 min-width:768px
	.wrapper.sidebar-collapse{
		@media (min-width:768px) {
			.main-sidebar{
				width: 50px;
				.user-panel{
					>.info{
						display: none;
					}
					.user-image{
						width: 30px;
						height: 30px;
					}
				}
				.sidebar-menu{
					.header{
						display: none;
					}
					li{
						text{
							display: none;
						}
						.pull-right{
							display: none;
						}
						.iconfont{
							padding-left: 2px;
						}
					}
				}
			}
		}
	}
	.wrapper.sidebar-open{
		border: 1px solid red;
		@media (max-width:768px){
			transform: translate(0,0) !important;
		}
	}
</style>