<template>
	<view class="register">
		<form class="register-form" @submit="toSign">
			<h1>注册</h1>
			<p>
				<label>用户名</label>
				<input type="text" neame="userName" placeholder="请输入用户名"/>
			</p>
			<p>
				<label>昵称</label>
				<input type="text" name="accountName" placeholder="请输入昵称"/>
			</p>
			<p>
				<label>邮箱</label>
				<input type="text" name="mailbox" placeholder="请输入邮箱"/>
			</p>
			<p>
				<label>密码</label>
				<input type="text" name="password" placeholder="请输入密码"/>
			</p>
			<p>
				<label>请重复输入密码 </label>
				<input type="text" name="againPassword" placeholder="请重复输入密码"/>
			</p>
			<p class="reset">
				<view>
					<button form-type="submit">SIGN UP</button>
				</view>
			</p>
			<p class="change-link">
				您已有账号？<text class="to-login" @click="toLogin()">去登录</text>
			</p>
		</form>
	</view>
</template>

<script>
	export default {
		name:"register",
		data() {
			return {
				
			};
		},
		methods:{
			toLogin(){
				uni.navigateTo({
					url:"/pages/login/login"
				})
			},
			toSign(e){
				console.log(e.detail.value)
			}
		}
	}
</script>

<style lang="scss">
	.register{
		border-radius: 5px;
	    position: absolute;
	    top: 0px;
	    width: 88%;
	    padding: 18px 6% 60px 6%;
	    margin: 0 0 35px 0;
	    background: rgb(247, 247, 247);
	    border: 1px solid rgba(147, 184, 189,0.8);
		.register-form{
			h1{
				background: repeating-linear-gradient(-45deg, rgb(18, 83, 93) , rgb(18, 83, 93) 20px, rgb(64, 111, 118) 20px, rgb(64, 111, 118) 40px, rgb(18, 83, 93) 40px);
				-webkit-background-clip: text;
				-webkit-text-fill-color: transparent;
				font-size: 48px;
			    color: rgb(6, 106, 117);
			    padding: 2px 0 10px 0;
			    font-weight: bold;
			    text-align: center;
			    padding-bottom: 30px;
				&::after{
				    content: ' ';
				    display: block;
				    width: 100%;
				    height: 2px;
				    margin-top: 10px;
				    background: -webkit-linear-gradient(left,rgba(147,184,189,0) 0%,rgba(147,184,189,0.8) 20%,rgba(147,184,189,1) 53%,rgba(147,184,189,0.8) 79%,rgba(147,184,189,0) 100%);
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
					&:not([type="checkbox"]){
						width: 92%;
						border-radius: 3px;
					    margin-top: 4px;
					    padding: 10px 5px 10px 32px;
					    transition: all 0.2s linear;
						border: 1px solid rgb(178, 178, 178);
					    -webkit-appearance: textfield;
					}
				}
				.to-login{
				    transition: all 0.4s linear;
				    border-radius: 4px;
				    border: 1px solid rgb(203, 213, 214);
				    display: inline-block;
				    font-weight: bold;
				    background: rgb(247, 248, 241);
				    padding: 2px 6px;
				    color: rgb(29, 162, 193);
				    margin-left: 10px;
				}
			}
			.reset{
			    text-align: right;
			    margin: 5px 0;
				view{
					&::hover{
						background: rgb(74, 179, 198);
					};
					background: rgb(74, 179, 198);
					width: 40%;
					cursor: pointer;
					padding: 8px 5px;
				    color: #fff;
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
			.change-link{
				@media (max-width:960px) {
					width: calc(88% - 21px)
				}
				width: 89%;
			    position: absolute;
			    color: rgb(127, 124, 124);
			    left: 0px;
			    padding: 17px 30px 20px 30px;
			    font-size: 16px;
			    text-align: right;
			    border-top: 1px solid rgb(219, 229, 232);
			    height: 20px;
				background: repeating-linear-gradient(-45deg, rgb(247, 247, 247) , rgb(247, 247, 247) 15px, rgb(225, 234, 235) 15px, rgb(225, 234, 235) 30px, rgb(247, 247, 247) 30px );
			}
		}
	}
</style>