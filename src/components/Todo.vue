<template>
<div style='margin-bottom: 10px;'>
 <div class="ui centered raised card" v-if="!isEditing">
	<div class="content">
		<div class="header">{{todo.title}}</div>
	</div>
	<div class="content">
		{{todo.desc}}
		<i class='remove red icon right floated'></i>
		<i class='write icon blue right floated' @click="showForm"></i>
	</div>
	<div v-if="todo.done" class="ui bottom blue attached button">Done <i class="checkmark icon"></i></div>
	<div v-if='!todo.done' class="ui bottom green attached button">Complete</div>
 </div>
  <div class="ui centered raised card" v-if="isEditing">
	  <div class="content">
	  	<div class="ui form">
	  		<div class="field">
	  			<label>Title</label>
	  			<input type="text" v-model="todo.title">
	  		</div>
	  		<div class="field">
	  			<label>Description</label>
	  			<input type="text" v-model="todo.desc">
	  		</div>
		 	<div class="ui teal attached button" @click="hideForm">Apply Changes</div>
	  	</div>
  </div>
  </div>
</div>
</template>

<script>
	export default{
		props:['todo'],
		data(){
			return{
				isEditing:false
			}
		},
		methods:{
			showForm(){
				this.isEditing=true;
			},
			hideForm(){
				this.isEditing=false;
			}
		}
	};
</script>