<template>
	<view class="nv-head">
		<view class="icon tf">
			<label>
				<i class="iconfont icon-24gf-tags"></i>
			</label>
		</view>
		<view class="search">
			<view class="search-box">
				<input type="text" placeholder="书名/作者/翻译" class="search-input input-word"/>
				<view class="icon-search to-search">
					<i class="iconfont icon-31sousuo"></i>
				</view>
			</view>
		</view>
		<view class="icon sort">
			<label>
				<i>
					<i class="iconfont icon-paixu"></i>
				</i>
			</label>
		</view>
	</view>
</template>

<script>
	export default {
		name:"nvHead",
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	.nv-head{
		@media screen and(max-width:960px){
			width: 100%;
		}
		width: 60%;
		margin: auto;
		display: grid;
		padding-left: 1rem;
		grid-template-columns: 4rem 4rem auto;
		grid-template-rows: 0rem;
		margin-top: 2rem;
		.icon{
			display: flex;
			justify-content: center;
			margin: auto;
			margin-top: 0.7rem;
			label{
				i{
					font-size: 1rem;
					font-weight: 700;
					transition: 0.3s ease;
					color: #9baacf;
				}
			}
		}
		.search{
			grid-column: 3/4;
			grid-row: 2/3;
			display: flex;
			padding-left: 0.5rem;
			.search-box{
				width: 25rem;
				height: 4rem;
				position: relative;
				@media screen and(max-width:960px){
					width: 10rem;
				}
				.search-input{
					@media screen and(max-width:960px){
						width: 10rem;
					}
					width: 25rem;
					height: 4rem;
					border: none;
					border-radius: 1rem;
					font-size: 1.2rem;
					padding-left: 1rem;
					padding-right: 3em;
					box-shadow:
						inset 0.2rem 0.2rem 0.5rem #c8d0e7,
						inset -0.2rem -0.2rem 0.5rem white;
					color:#9baacf;
				}
				.icon-search{
					height: 2rem;
					position: absolute;
					font-size: 2rem;
					padding: 0 1rem;
					display: flex;
					color: #9baacf;
					right:0;
					top: 0.7em;
				}
			}
		}
	}
</style>