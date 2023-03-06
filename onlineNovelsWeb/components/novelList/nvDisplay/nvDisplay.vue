<template>
	<view class="store-list-display" :classify="classify">
		<view class="store-leg">
			<!--分割提示线-->
			<hr class="hr-solid-content">
			<view class="list-card" v-for="item in listStory" @click="gotoNovel(item.novelId)">
				<a><view class="list-card-header">{{item.title}}</view></a>
				<view class="list-card-body">
					<a>
						<image class="store-img" :src="item.ImageSrc"></image>
					</a>
					<view class="store-info">
						<view class="author" v-if="item.author">作者: {{item.author}}</view>
						<view class="translator" v-if="item.classify">翻译: <span class="ts" v-for="ts in item.translators">{{ts}}</span></view>
						<view class="tags">
							标签: 
							<span class="tag" v-for="tag in item.tags">{{tag}}</span>
						</view>
						<view class="words">字数: {{item.words}}字共{{item.chapter.length}}话</view>
						<view class="hots">热度: {{item.hots.commentsMath}}评论 {{item.hots.likeMath}}点赞 {{item.hots.collectionMath}}收藏</view>
						<a>
							<view class="newup">最新: {{item.chapter[item.chapter.length-1]}} </view>
						</a>
					</view>
				</view>
				<view class="list-card-footer" v-if="item.limit">限制等级:{{item.limit}}</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"nvDisplay",
		props:["classify"],
		data() {
			return {
				listStory:"",
			};
		},
		methods:{
			gotoNovel(novelId){
				console.log(novelId)
				uni.navigateTo({
					url:`/pages/novelRead/novelRead?novelId=${novelId}`
				})
			}
		},
		created() {
			console.log("开始请求"),
			uni.request({
				url:"/api/listStory",
				method:'POST',
				data: {
				    classify: Number(this.classify)
				},
				success:(res)=>{
					console.log(res.data)
					this.listStory=res.data
				}
			})
		}
	}
</script>

<style lang="scss">
	.store-list-display{
		border: none;
		margin: 10px 0 20px;
		.store-leg{
			font-weight: 300;
			font-size: 20px;
			padding: 0 10px;
			display: grid;
			justify-content: space-around;
			grid-gap: 10px;
			grid-template-columns: repeat(auto-fill,minmax(300px,1fr));
			.hr-solid-content{
				color: #a2a9b6;
				font-size: 12px;
				padding: 1em 0;
				position: relative;
				&::before{
					content: "第1页 共31页 914本";
					position: absolute;
					padding: 0 1ch;
					line-height: 1px;
					border:solid #d0d0d5;
					border-width: 0 99vw;
					width: fit-content;
					white-space: nowrap;
					left: 50%;
					transform: translateX(-50%);
				}
			}
			hr{
				background-color: #e6e6e6;
				height: 1px;
				clear: both;
				margin: 10px 0;
			}
			.list-card{
				margin-bottom: 15px;
				border-radius: 2px;
				background-color: #FFF;
				box-shadow: 0 1px 2px rgba(0, 0, 0, .1);
				max-width: 400px;
				cursor: pointer;
				font-size: 10px;
				height: 250px;
				// a{
				// 	color: #333;
				// 	text-decoration: none;
				// }
				.list-card-header{
					position: relative;
					height: 42px;
					line-height: 42px;
					padding: 0 15px;
					border-bottom: 1px solid #f6f6f6;
					color: #333;
					overflow: hidden;
					font-weight: 800;
					text-overflow: ellipsis;
					white-space: nowrap;
					text-align: center;
				}
				.list-card-body{
					position: relative;
					padding: 10px 15px;
					line-height: 24px;
					display: grid;
					grid-template-columns: min-content auto;
					grid-gap: 5px;
					.store-img{
						// display: inline-block;
						width: 120px;
						height: 166px;
						padding: 4px;
						background-color: #fff;
						border: 1px solid #ddd;
						border-radius: 4px;
						vertical-align: middle;
					}
					.store-info{
						display: flex;
						flex-wrap: wrap;
						min-height: 130px;
						max-height: 160px;
						margin: 0px 0px auto 5px;
						word-wrap: break-word;
						word-break: normal;
						line-height: 22px;
						font-size: 12px;
						color: black;
						.tags{
							display: box;
							line-clamp: 2;
							box-orient: vertical;
							overflow: hidden;
							.tag{
								padding: 2px;
							}
						}
						.author,.words,.hots,.translators{
							display: -webkit-box;
							-webkit-line-clamp: 1;
							-webkit-box-orient: vertical;
							overflow: hidden;
						}
						.ts{
							margin-right: 3px;
						}
					}
				}
				.list-card-footer{
					text-align: right;
					padding-right: 10px;
					color: red;
					font-size: 10px;
				}
			}
		}
	}
</style>