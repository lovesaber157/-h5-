<template>
	<view class="lay-tab lay-tab-brief">
		<ul class="lay-tab-title">
			<li :class="index?'':'lay-this'" v-for="(item,index) in leaderboard" @click="changeList(index)" :key="index">
				{{item.type?'总':'月'}}榜
			</li>
		</ul>
		<view class="lay-tab-content">
			<view class="lay-tab-item lay-show">
				<view class="fr">
					<view class="card">
						<view class="card-head">
							月收藏数排行
						</view>
						<hr class="layui-bg-green">
						<view  v-for="item in leaderboard[0].detail.collection">
							<text>{{item.title}}</text>
							<text class="rank-nums">收藏数:{{item.math}}</text>
							<hr class="layui-bg-gray">
						</view>
					</view>
				</view>
				<view class="fl">
					<view class="card">
						<view class="card-head">
							月评论数排行
						</view>
						<hr class="layui-bg-green">
						<view v-for="item in leaderboard[0].detail.comment">
							<text>{{item.title}}</text>
							<text class="rank-nums">评论数:{{item.math}}</text>
							<hr class="layui-bg-gray">
						</view>
					</view>
				</view>
			</view>
			<view class="lay-tab-item">
				<view class="fr">
					<view class="card">
						<view class="card-head">
							总收藏数排行
						</view>
						<hr class="layui-bg-green">
						<view v-for="item in leaderboard[0].detail.collection">
							<text>{{item.title}}</text>
							<text class="rank-nums">收藏数:{{item.math}}</text>
							<hr class="layui-bg-gray">
						</view>
					</view>
				</view>
				<view class="fl">
					<view class="card">
						<view class="card-head">
							总评论数排行
						</view>
						<hr class="layui-bg-green">
						<view v-for="item in leaderboard[0].detail.comment">
							<text>{{item.title}}</text>
							<text class="rank-nums">评论数:{{item.math}}</text>
							<hr class="layui-bg-gray">
						</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"tabList",
		data() {
			return {
				type:0,
				leaderboard:[
					{
						type:0, //总榜
						detail:{
							comment:[
								{
									title:"不正经小说（瑟瑟小说） ",
									math:1843
								},
								{
									title:"真白萌猫猫咖啡店 ",
									math:1646
								}
							],
							collection:[
								{
									title:"真白萌猫猫咖啡店",
									math:256825
								},
								{
									title:"异世界狂想曲",
									math:80086
								},
							]
						}
					},
					{
						type:1, //月榜
						detail:{
							comment:[
								{
									title:"不正经小说（瑟瑟小说） ",
									math:1843
								},
								{
									title:"真白萌猫猫咖啡店 ",
									math:1646
								}
							],
							collection:[
								{
									title:"真白萌猫猫咖啡店",
									math:256825
								},
								{
									title:"异世界狂想曲",
									math:80086
								},
							]
						}
					}
				]
			};
		},
		methods:{
			changeList(liIndex){
				let otherIndex=liIndex?0:1
				let liList=document.getElementsByClassName("lay-tab-title")[0].children
				let viewList=document.getElementsByClassName("lay-tab-item")
				if(!liList[liIndex].className){
					liList[liIndex].className="lay-this"
					liList[otherIndex].className=""
					viewList[liIndex].classList+=" lay-show"
					viewList[otherIndex].className="lay-tab-item"
				}
			}
		}
	}
</script>

<style lang="scss">
	@import "@/static/public.scss";
	.lay-tab{
		margin: 10px 0;
		text-align: left;
	}
	.lay-tab-title{
		margin: 0;
		padding: 0;
		border-color: #e6e6e6;
		position: relative;
		left: 0;
	    height: 40px;
	    white-space: nowrap;
	    font-size: 0;
	    border-bottom-width: 1px;
	    border-bottom-style: solid;
		transition: all .2s;
		.lay-this{
			color: #009688;
		}
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
	}
	.lay-tab-content{
		padding: 10px;
		.lay-tab-item{
			display: none;
		}
		.lay-show{
			display: block;
			.fr{
				@media screen and (max-width:960px){
					float: left;
					width: 100%;
					.card{
						float: none;
					}
				}
				float: left;
				width: 49%;
				.card{
					width: 100%;
					position: relative;
					margin-left: 0;
				    margin-right: 0;
				    height: auto;
				    zoom: 1;
				    display: block;
				    border: 1px solid #eee;
				    border-radius: 6px;
				    margin-top: 20px;
					transition: all 0.2s ease-in-out;
				    background: white;
				    min-height: 200px;
				    padding: 5px;
				}
			}
			.fl{
				@media screen and (max-width:960px){
					float: left;
					width: 100%;
				}
				float: right;
				width: 49%;
				.card{
					width: 100%;
					position: relative;
					margin-left: 0;
				    margin-right: 0;
				    height: auto;
				    zoom: 1;
				    display: block;
				    border: 1px solid #eee;
				    border-radius: 6px;
				    margin-top: 20px;
					transition: all 0.2s ease-in-out;
				    background: white;
				    min-height: 200px;
				    padding: 5px;
				}
			}
			.rank-nums{
				color: #1073c9;
				font-size: 8px;
				transform: scale(0.7);
				padding-left: 2px;
			}
		}
	}
</style>