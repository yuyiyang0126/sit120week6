<template>
<div class="checklist">
		<div class="info">
			<div class="title">Mod Check List For My Car</div>
			<div class="list">
				<dl v-for="(item,index) in msgArr"><dt><input type="checkbox"></dt><dd>{{item}}</dd></dl>
			</div>
			<div class="form">
				<input type="text" v-model.lazy="msg" ref="msg"><button @click="addMsg()">ADD</button>
			</div>
            <div id="v-model-select-dynamic" class="wheel">
            <select v-model="selected">
                <option v-for="option in options" v-bind:value="option.value">
                   {{ option.text }}
                 </option>
            </select>
         <span>  Selected: {{ selected }}</span>
         <div class="thumb"><img src="../assets/img/img02.png" ></div>
		</div>
	</div>
</div>
</template>
<script>
export default{
	data() {
		return {
			msg:'',
			msgArr:[],
            selected: 'Stock Rims',
            options: [
            { text: 'One', value: 'Stock Rims' },
            { text: 'Two', value: 'Rays Rims' },
            { text: 'Three', value: 'Bbs Rims' }]  
			
		}
	},
	methods:{
		addMsg(){
			if(this.msg==''){
				this.$refs.msg.style.border="1px solid red";
				return false;
			}
			
			this.msgArr.push(this.msg);
			this.msg='';
		}
	}
}	
</script>
<style scoped="scoped">
.checklist{ display: flex; justify-content: space-between; flex-wrap: wrap; padding: 20px; top: 100px;}	
.checklist .info{background:#c4c4c4; overflow: hidden; }
.checklist .title{ font-size:30px; background: #b7acac; line-height: 40px; text-indent: 10px; font-family: orbitron;}
.checklist .list{ padding: 10px; font-family: orbitron; }
.checklist .list dl{display:flex; align-items: center; margin-bottom: 10px;}
.checklist .list dl dt{ margin-right: 5px;}
.checklist .list dl dt input{width: 15px; height:15px;}
.checklist .list dl dd{font-size: 25px;}
.checklist .form{ padding: 0 10px;}
.checklist .form input{width:200px; height:42px; background:#fff; border:1px solid #fff; text-indent: 5px; font-size: 20px;padding-top: 8px;}
.checklist .form button{width: 80px; height: 3px; background: #3a00f3; color:black; cursor: pointer; font-family: orbitron; padding-bottom: 42px;  }
.checklist .wheel{ float:left; padding:30px 10px 30px; font-family: orbitron; text-align-last: center;}
@media(max-width:768px ){
 .info{ margin-bottom:30px; height:auto; }
 .thumb img{width:100%;}
}


</style>