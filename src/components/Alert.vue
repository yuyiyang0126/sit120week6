<template>
<div class="root">
	<div class="alert" v-show="show">
		<div class="btn"><a href="javascript:;" @click="btnClose()">×</a></div>
		<div class="msg">
			<slot name="header"></slot>
			<div class="v">{{msg}}</div>
		</div>
	</div>
</div>	
</template>

<script>
export default {
	name:'Alert',
	props:['msg'],
	data() {
		return {
			show:false,
		}
	},
	methods:{
		btnClose(){
			this.show=!this.show
		}
	}
}
</script>

<style scoped="scoped">
.alert{width:300px; height: auto; overflow: hidden; background: rgb(250, 219, 219); position: fixed; top: 120px; left: 50%; transform: translate(-50%,0);}
.alert .btn{position: absolute; right: 0;}
.alert .btn a{display: block; width: 20px; height: 20px; background: red; color: #fff; text-align: center; line-height: 20px; border-radius: 100%;}
.alert .msg{padding: 30px 0; text-align: center;}
</style>
