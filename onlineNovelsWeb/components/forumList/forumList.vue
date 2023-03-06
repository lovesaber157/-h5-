<template>
	<view id="app">
		<section class="content-header">
			<view id="h1">论坛一览<small></small></view>
		</section>
		<section class="content">
			<view class="row">
				<view class="col-12">
					<view class="list-box">
						<view class="list-head">
							<form>
								<view class="search-wrapper">
									<view class="search-input">
										<input type="text" placeholder="请输入关键词" class="search"/>
										<button class="search-button">
											<i class="iconfont icon-31sousuo"></i>
										</button>
									</view>
								</view>
							</form>
						</view>
						<view class="list-body">
							<view class="forum-box" v-for="item in forumList" :key="item.forumId" @click="goToForum(item.forumId)">
								<view class="forum-box-left">
									<image :src="item.img" class="forum-logo"></image>
								</view>
								<view class="forum-box-right">
									<view class="f-name">
										{{item.name}}
									</view>
									<view class="f-info">
										{{item.info}}
									</view>
								</view>
							</view>
						</view>
						<view class="list-floot">
							<ul class="pagination">
								<li class="page-item disable">
									<span>《</span>
								</li>
								<li class="page-item active">
									<span>1</span>
								</li>
								<li class="page-item">
									<span>2</span>
								</li>
								<li class="page-item">
									<span>》</span>
								</li>
							</ul>
						</view>
					</view>
				</view>
			</view>
		</section>
	</view>
</template>

<script>
	export default {
		name:"forumList",
		props:{
			type:Number
		},
		data() {
			return {
				forumList:[]
			};
		},
		created() {
			uni.request({
				url:"/api/ForumList",
				method:'POST',
				data:{
					type:this.type
				},
				success:(res)=>{
					this.forumList=res.data
				}
			})
		},
	}
</script>

<style lang="scss">
	@import "@/static/scss/public.scss";
	.list-head{
		width: 100%;
		height: 80px;
		margin: 10px 0;
		.search-wrapper{
			position: absolute;
			top: 40px;
			left: 50%;
			transform: translate(-50%,-50%);
			.search-input{
				@media screen and(max-width:540px){
					width: 200px;
				}
				border-radius: 50px;
				width: 450px;
				background-color: rgba(19, 63,70, 0.25);
				transition: all .5s cubic-bezier(0,0.105,0.035,1.570);
				overflow: hidden;
				height: 70px;
				position: relative;
				.search{
					opacity: 1;
					transform: translate(0,10px);
					width: 100%;
					height: 50px;
					padding: 0 70px 0 20px;
					position: absolute;
					top: 0;
					left: 0;
					font-size: 16px;
					font-weight: 400;
					line-height: 20px;
					color: #FFF;
					transition: all .3s cubic-bezier(0,0.105,0.035,1.570);
					transition-delay: 0.3s;
					margin: 0;
				}
				.search-button{
					width: 50px;
					height: 50px;
					margin: 10px;
					border-radius: 30px;
					position: relative;
					float: right;
					padding: 0;
					transition: all .3s ease-in-out;
				}
			}
		}
	}
	.list-body{
		@media screen and(max-width:780px){
			display: flex;
			flex-wrap: wrap;
			justify-content: space-evenly;
		}
		display: grid;
		grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
		.forum-box{
			&:hover{
				box-shadow: 5px 10px 10px 1px #494f5285;
				transform: scale(1.1,1.1);
			}
			@media screen and(max-width:640px){
				width: 90%;
				height: 270px;
				margin: 0 0 40px 0;
			}
			width: 15em;
			font-size: 13px;
			height: 20em;
			background-color: white;
			margin: 0 0.8em 2em 0.8em;
			display: flex;
			flex-direction: column;
			padding: 0;
			box-shadow: 0 1px 5px 1px rgb(0 ,0, 0 / 10%);
			border-radius: 1em;
			cursor: pointer;
			transition: all .6s cubic-bezier(0.165, 0.84, 0.44, 1);
			.forum-box-left{
				@media screen and (max-width:640px){
					height: 140px;
				}
				float:left;
				height: 65%;
				.forum-logo{
					@media screen and(max-width:640px){
						height: 270px;
					}
					object-fit: cover;
					height: 20em;
					border-radius: 1em;
					width: 100%;
					vertical-align: middle;
				}
			}
			.forum-box-right{
					@media screen and (max-width:640px){
						height: 140px;
					}
					float:right;
					position: relative;
					width: 100%;
					height: 35%;
					padding: 0.6em 0.6em 0.4em 0.6em;
					display: flex;
					flex-direction: column;
					color: white;
					border-radius: 0px 0px 1em 1em;
					background-image: linear-gradient(0deg,black,transparent);
					.f-name{
						@media screen and(max-width:640px){
							font-size: 17px;
						}
						font-size: 1.1em;
						font-weight: 600;
						text-shadow: #000000c9 1px 1px 0.3em;
					}
					.f-info{
						@media screen and(max-width:640px){
							font-size: 13px;
						}
						font-size: 0.8em;
						overflow: hidden;
						white-space: normal;
						text-overflow: ellipsis;
						text-shadow: #000000c9 1px 1px 0.3em;
					}
				}
			}
		}
		.list-floot{
			width: 100%;
			.pagination{
				float: right;
				display: inline-block;
				padding-left: 0;
				margin: 20px 0;
				border-radius: 4px;
				cursor: pointer;
				li{
					display: inline;
					span,a{
						position: relative;
						float: left;
						padding: 6px 12px;
						margin-left: -1px;
						line-height: 1.42857143;
						color: #337ab7;
						text-decoration: none;
						background-color: #fff;
						border: 1px solid #ddd;
					}
				}
				li:first-child,li:last-child{
					margin-left: 0;
					border-top-left-radius: 4px;
					border-bottom-left-radius: 4px;
				}
				.disable{
					span,a,a:focus,a:hover,span:focus,span:hover{
						color: #777;
						cursor: not-allowed;
						background-color: #fff;
						border-color: #ddd;
					}
				}
				.active{
					span,a,a:focus,a:hover,span:focus,span:hover{
						z-index: 2;
						color: #fff;
						cursor: default;
						background-color: #337ab7;
						border-color: #337ab7;
					}
				}
			}
		}
	
</style>