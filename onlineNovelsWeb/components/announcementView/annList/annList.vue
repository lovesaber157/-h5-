<template>
	<view class="card">
		<fieldset class="layui-elem-field layui-field-title" style="margin-top: 30px;">
			<legend style="border-bottom: none;width: 100px;">公告一览</legend>
		</fieldset>
		<view class="layui-collapse">
			<view v-for="(item,index) in announcementList">
				<view class="layui-colla-item">
					<view class="h2 layui-colla-title"  @click="changeStates(index)">
						{{item.title}}
						<span class="time">{{item.time}}</span>
						<i class="iconfont icon-zhankai icon"></i>
					</view>
					<view class="announcement-show" v-show="item.show">						
						{{item.thumbnail}} 
						<a @click="goToAn(item.annid)">查看全部</a>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"annList",
		data() {
			return {
				announcementList:[]
			};
		},
		created() {
			let that=this
			uni.request({
				url:"/api/announcementList",
				method:'POST',
				success(res) {
					that.announcementList=res.data
				}
			})
		},
		methods:{
			changeStates(index){
				let viewElements=document.getElementsByClassName('icon')[index]
				if(viewElements.className==="iconfont icon-zhankai"){
					viewElements.className="iconfont icon-zhankai1"
					this.announcementList[index].show=!this.announcementList[index].show
				}else{
					viewElements.classList="iconfont icon-zhankai"
					this.announcementList[index].show=!this.announcementList[index].show
				}
			},
			goToAn(annid){
				uni.navigateTo({
					url:"/pages/annDetail/annDetail?annId="+annid
				})
			}
		}
	}
</script>

<style lang="scss">
	.card{
		display: block;
		width: 100%;
		position: relative;
		height: auto;
		margin-left: 0;
		margin-right: 0;
		border: 1px solid #eee;
		border-radius: 6px;
		margin-top: 20px;
		background: white;
		min-height: 500px;
		padding: 10px;
		transition: all .2s ease-in-out;
	}
	.layui-field-title{
		border-width: 1px 0 0;
		margin: 10px 0 20px;
	}
	fieldset{
		min-width: 0;
	}
	.layui-elem-field{
		border-color: #e6e6e6;
		margin-bottom: 10px;
		padding: 0;
		legend{
			margin-left: 20px;
			padding: 0 10px;
			font-size: 20px;
			font-weight: 300;
		}
	}
	legend{
		display: block;
		margin-bottom: 20px;
		line-height: inherit;
		color: #333;
		border: 0;
	}
	.layui-collapse{
		border: #e6e6e6;
		border-width: 1px;
		border-style: solid;
		border-radius: 2px;
	}
	.layui-colla-item:first-child{
		border-top: none;
	}
	.layui-colla-item{
		border-color: #e6e6e6;
	}
	.layui-colla-title{
		margin: 0 !important;
		position: relative;
		height: 42px;
		line-height: 42px;
		padding: 0 15px 0 35px;
		color: #333;
		background-color: #f2f2f2;
		cursor: pointer;
		font-size: 14px;
		overflow: hidden;
	}
	.time{
		font-size: 10px;
		transform: scale(0.8);
		line-height: 25px;
		margin-left: 10px;
	}
	.iconfont{
		position: absolute;
		left: 15px;
		top: 0;
		font-size: 14px;
	}
	.announcement-show{
		border: 1px solid #e6e6e6;
		line-height: 44rpx;
		color: #666; 
		padding: 20rpx 30rpx;
		a{
			color: #3c8dbc;
			padding-left: 20rpx;
		}
	}
</style>