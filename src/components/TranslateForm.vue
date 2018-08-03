<template>
	<div class="row" id="translateForm">
		<div class="col-md-6 col-md-offset-3">
		  <form id="transforms" class="well form-inline" v-on:submit="formSubmit">
		  	<input type="text" class="form-control" v-model="textToTranslate" placeholder="输入需要翻译的内容" />
		  	<select class="form-control" v-model="language">
		  		<option value="en">English</option>
		  		<option value="ru">Russian</option>
		  		<option value="ko">Korean</option>
		  		<option value="ja">Janpenese</option>
		  		<option value="ht">Haitian (Creole)</option>
		  	</select>
		  	<input class="btn btn-primary" type="submit" value="翻译"/>
		  </form>
		  </div>
	</div>
</template>

<script>
	export default{
		name:'translateFrom',
		data:function(){
			return{
				textToTranslate:"",
				language:""
			}
		},
		methods:{
			formSubmit:function(){
				//alert(this.textToTranslate);
				this.$emit("formDelivery",this.textToTranslate,this.language);
				e.preventDefault();
			}
		},
		created:function(){
			this.language="en";
		}
	}
</script>

<style>
	#transforms{
		border-radius: 10px;
		border: 1px #ccc solid;
	}
</style>