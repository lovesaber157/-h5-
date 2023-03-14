<template>
	<view class="container">
		<header>
			<nav class="codrops-demos">
				<h1>Masiro</h1>
			</nav>
		</header>
		<section>
			<view id="container-from">
				<view class="wrapper">
					<view class="login">
						<form @submit="formSubmit">
							<h1>登录</h1>
							<p>
								<label>账号</label>
								<input class="input-control" name="username" placeholder="请输入用户名或邮箱"/>
							</p>
							<p>
								<label>密码</label>
								<input class="input-control" name="password" placeholder="请输入账号密码"/>
							</p>
							<P class="keepLogin">
								<checkbox name="remember" value="1"></checkbox>
								<label>记住密码</label>
							</P>
							<p class="login-button">
								<view>
									<button form-type="submit">LOGIN</button>
								</view>
							</p>
							<p class="change">
								<view @click="changeShow()">去注册</view>
							</p>
						</form>
					</view>
					<register v-show="registerShow"></register>
				</view>
			</view>
		</section>
	</view>
</template>

<script>
	import register from "@/components/login/register/register.vue"
	export default {
		name:"login",
		components:{register},
		data() {
			return {
				registerShow:false,
				userAccountName:"",
				userPassword:""
			};
		},
		methods:{
			changeShow(controlMath){
				this.registerShow=!this.registerShow
			},
			formSubmit(e){
				console.log('form发生了submit事件，携带数据为：' + JSON.stringify(e.detail.value))
				if(e.detail.value.username=="root"&&e.detail.value.password=="123"){
					uni.navigateTo({
						url:"/pages/index/index"
					})
				}else{
					uni.showToast({
						title:"账号或密码错误",
						position:"center",
						icon:"error"
					})
				}
			}
		}
	}
</script>

<style lang="scss">
	.container{
		width: 100%;
		height: 100%;
		position: relative;
		text-align: center;
		.header{
			padding: 20px 30px 10px 30px;
			margin: 0px 20px 10px 20px;
			position: relative;
			display: block;
			.codrops-demos{
				display: block;
				padding: 14px;
			}
		}
	}
	.container-from{
		text-align: left;
		padding: 0;
		margin: 0 auto;
	}
	.wrapper{
		@media screen and (max-width: 960px){
			width: calc(100% - 20px);
		}
		min-height: 560px;
		margin: 0px auto;
		width: 500px;
		position: relative;
		.login{
			border-radius: 5px;
			position: absolute;
		    top: 0px;
		    width: 88%;
		    padding: 18px 6% 60px 6%;
		    margin: 0 0 35px 0;
		    background: rgb(247, 247, 247);
		    border: 1px solid rgba(147, 184, 189,0.8);
			h1{
				&::after{
					content: ' ';
					display: block;
					width: 100%;
					height: 2px;
					margin-top: 10px;
					background: 
						-webkit-linear-gradient(left, rgba(147,184,189,0) 0%,rgba(147,184,189,0.8) 20%,rgba(147,184,189,1) 53%,rgba(147,184,189,0.8) 79%,rgba(147,184,189,0) 100%);
				}
			}
			p{
				margin-bottom: 15px;
				label{
					color: rgb(64, 92, 96);
					position: relative;
					&::after{
					    color: rgb(106, 159, 171);
					    position: absolute;
					    left: 10px;
					    top: 35px;
					    width: 30px;
					}
				}
				input{
					text-align: left;
				    transition: all 0.2s linear;
					width: 92%;
				    margin-top: 4px;
				    padding: 10px 5px 10px 32px;
				    border: 1px solid rgb(178, 178, 178);
				    -webkit-appearance: textfield;
				}
			}
		}
		.keepLogin{
			label{
				width: 80%;
			    display: inline-block;
			    font-size: 12px;
			    font-style: italic;
				text-align: left;
			}
		}
		.login-button{
		    text-align: right;
		    margin: 5px 0;
			view{
				&::hover{
					background: rgb(74, 179, 198);
				};
				background: rgb(74, 179, 198);
				width: 30%;
				cursor: pointer;
				padding: 8px 5px;
				border-radius: 3px;
				transition: all 0.2s linear;
			    font-size: 24px;
			    border: 1px solid rgb(28, 108, 122);
			    margin-bottom: 10px;
				text-align: left;
				display: inline-block;
				button{
					color: #fff;
					background: rgb(74, 179, 198);
					&::after{
						border: none;
					}
				}
			}
		}
	}
	.change{
		@media screen and (max-width: 960px){
		    width: calc(88% - 21px)
		}
		width: 89%;
	    position: absolute;
	    color: rgb(127, 124, 124);
	    left: 0px;
	    height: 20px;
		background: repeating-linear-gradient(-45deg, rgb(247, 247, 247) , rgb(247, 247, 247) 15px, rgb(225, 234, 235) 15px, rgb(225, 234, 235) 30px, rgb(247, 247, 247) 30px );
		padding: 17px 30px 20px 30px;
		font-size: 16px;
		border-radius: 0 0 5px 5px;
		text-align: right;
		border-top: 1px solid rgb(219, 229, 232);
		view{
			display: inline-block;
		    font-weight: bold;
		    background: rgb(247, 248, 241);
		    padding: 2px 6px;
		    color: rgb(29, 162, 193);
		    margin-left: 10px;
			transition: all 0.4s linear;
			border-radius: 4px;
			border: 1px solid rgb(203, 213, 214);
		}
	}
</style>