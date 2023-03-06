<template>
	<view class="new-update-box card">
		<view class="update-head">
			<a>最近更新</a>
			<view class="update-top-titles">
				<view class="title" @click="changeCards(0)">翻译</view>
				<view class="title" @click="changeCards(1)">原创</view>
			</view>
		</view>
		<hr class="layui-bg-green">
		<view class="tab-item">
			<!--翻译-->
			<view class="update-cards" v-show="cardsToShow">
				<view v-for="(item,index) in storyInfo">
					<a @click="checkStore()">
						<view class="card-item">
							<view class="card-image-box">
								<image :src="item.imageSrc" class="card-image"></image>
							</view>
							<view class="card-info">
								<view class="update-store-title">
									{{item.storeTitle}}
								</view>
								<view class="update-store-chapter">
									{{item.upDateChapter}}
								</view>
							</view>
							<view class="time">2小时前</view>
						</view>
					</a>
				</view>
			</view>
			<!--原创-->
			<view class="update-cards" v-show="!cardsToShow">
				<view v-for="(item,index) in originalStory">
					<a @click="checkStore()">
						<view class="card-item">
							<view class="card-image-box">
								<image :src="item.imageSrc" class="card-image"></image>
							</view>
							<view class="card-info">
								<view class="update-store-title">
									{{item.storeTitle}}
								</view>
								<view class="update-store-chapter">
									{{item.upDateChapter}}
								</view>
							</view>
							<view class="time">2小时前</view>
						</view>
					</a>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"newUp",
		data() {
			return {
				cardsToShow:true,
				//最近更新
				storyInfo:[
					{
						storeTitle:"转生为魔剑",
						upDateChapter:"web本篇 web第1149章 高等级冒险者们",
						imageSrc:require("@/static/photos/storeimg01.jpg"),
						upDateTime:"16:04:20"
					},
					{
						storeTitle:"转生成小小妖精",
						upDateChapter:"web 第三章 魔物狂潮 072 藥水",
						imageSrc:require("@/static/photos/storeimg05.jpg"),
						upDaterTime:"08:00:03"
					},
					{
						storeTitle:"转生成小小妖精",
						upDateChapter:"web 第三章 魔物狂潮 072 藥水",
						imageSrc:require("@/static/photos/storeimg05.jpg"),
						upDaterTime:"08:00:03"
					},
					{
						storeTitle:"转生成小小妖精",
						upDateChapter:"web 第三章 魔物狂潮 072 藥水",
						imageSrc:require("@/static/photos/storeimg05.jpg"),
						upDaterTime:"08:00:03"
					}
				],
				//原创
				originalStory:[
					{
						storeTitle:"即便如此 我们……",
						upDateChapter:"来自〇〇的选召 第十二章 学园活动--2",
						imageSrc:require("@/static/photos/storeimg06.jpg"),
						upDaterTime:"15:56:25"
					},
					{
						storeTitle:"来成为年度最垃圾的恶役千金吧？我才不要！",
						upDateChapter:"正文 第一百二十一幕 夜语",
						imageSrc:require("@/static/photos/storeimg07.png"),
						upDaterTime:"12:18:26"
					},
					{
						storeTitle:"惡女之復仇~我是反派千金的替身~",
						upDateChapter:"卷一 簡單的異世界攻略法 (61) 從此我們開始了互相較勁 ",
						imageSrc:require("@/static/photos/storeimg08.jpg"),
						upDaterTime:"12:18:26"
					},
					{
						storeTitle:"编织谎言的吸血鬼与被遗弃的世界",
						upDateChapter:"Part.2 『不夜之城的摇篮曲』 Stage.3 芙莱尔",
						imageSrc:require("@/static/photos/storeimg09.jpg"),
						upDaterTime:"12:18:26"
					}
				]
				//随机推荐
			};
		},
		methods:{
			changeCards(controlMath){
				this.cardsToShow=!this.cardsToShow
				let divElements=document.getElementsByClassName("title")
				if(controlMath){
					divElements[controlMath].className="title lay-this"
					divElements[controlMath-1].className="title"
				}else{
					divElements[controlMath].className="title lay-this"
					divElements[controlMath+1].className="title"
				}
			},
			checkStore(){
				uni.navigateTo({
					url:"/pages/storyInfo/storyInfo"
				})
				console.log("点击本书")
			}
		},
		computed:{
			toShowTime(){
				let nowTime=new Date()
				let upDateTime=this.storyInfo[0].upDateTime.split(":")
				let upDateHours=Number(upDateTime[0])
				let upDateMinutes=Number(upDateTime[1])
				let upDateSeconds=Number(upDateTime[2])
				if(Number(nowTime.getHours())-upDateHours){
					return Number(nowTime.getHours())-upDateHours
				}else{
					if(Number(nowTime.getMinutes())-upDateMinutes){
						return Number(nowTime.getMinutes())-upDateMinutes
					}else{
						if(Number(nowTime.getSeconds())-upDateSeconds){
							return Number(nowTime.getSeconds())-upDateSeconds
						}
					}
				}
			}
		}
	}
</script>

<style lang="scss">
	@import "@/static/public.scss";
	.update-head{
		padding: unset;
		display: flex;
		justify-content: space-between;
	}
	.update-top-titles{
		display: flex;
		.title{
			color: grey;
			margin: 0 18rpx;
		}
	}
</style>