<template>
	<view id="center-body">
		<view class="layui-tab">
			<ul class="layui-tab-title">
				<li @click="changeLay(index)" :key="index" :class="item.isDefault?'layui-this':''" v-for="(item,index) in tabTitle">{{item.titleName}}</li>
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
				<view class="layui-tab-item">
					<view>
						
					</view>
				</view>
				<view class="layui-tab-item lay-show">
					<view class="zl-grid">
						<view class="card">
							<view class="card-head">
								<text>翻译小说:《关于转生成日式幻想黄油路人这件事》</text>
							</view>
							<hr class="lay-bg-green">
							<text>公告 作者正在募集插画 </text>
							<br>
							<text>第二章 关于安全区偶尔也会因游戏事件而消失的事 第九话 </text>
						</view>
					</view>
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
				tabTitle:[
					{
						isDefault:true,
						titleName:"帖子",
					},
					{
						isDefault:false,
						titleName:"关注"
					},
					{
						isDefault:false,
						titleName:"粉丝"
					},
					{
						isDefault:false,
						titleName:"资历"
					}
				],
				defaultClassName:[]
			};
		},
		methods:{
			changeLay(liIndex){
				if(!this.tabTitle[liIndex].isDefault){
					for(let i of this.tabTitle){
						if(i.isDefault===true){
							i.isDefault=!i.isDefault
							break
						}
					}
					this.tabTitle[liIndex].isDefault=!this.tabTitle[liIndex].isDefault
				}
			}
		},
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
	.zl-grid{
		@media (max-width:960px) {
			grid-template-columns: 100%;
		}
		display: grid;
	    grid-template-columns: 50% 50%;
	}
	.card{
		width: 98%;
	    transition: all 0.2s ease-in-out;
	    background: white;
	    min-height: 200px;
	    padding: 10px;
	    max-height: 500px;
	    overflow: auto;
		display: block;
	    border: 1px solid #eee;
	    border-radius: 6px;
	    margin-top: 20px;
		.card-head{
		    width: 100%;
		    padding: 10px;
		    height: 33px;
		    font-size: 17px;
		    text-align: left;
		    font-weight: 600;
		    line-height: 30px;
		    overflow: hidden;
		    text-overflow: ellipsis;
		    white-space: nowrap;
			text{
				display: inline !important;
			}
		}
		.lay-bg-green{
			background-color: #009688;
		}
		hr{
			clear: both;
			margin: 10px 0;
			margin-top: 20px;
		    margin-bottom: 20px;
		    border: 0;
		    border-top: 1px solid #eee;
		}
		text{
			color: #3c8dbc;
			cursor: pointer;
			display: inline-block;
			margin-top: 5px;
		}
	}
</style>