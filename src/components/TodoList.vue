<template>
	<div>
	<h1 class="ui header centered">Todo App</h1>
	<div class="ui center aligned segment">
		<h3>Completed Tasks - {{todos.filter(todo=>todo.done).length}}</h3>
		<h3>Pending Tasks - {{todos.filter(todo=>!todo.done).length}}</h3>
		<div class="ui centered black button" v-if="!add" @click="add=!add">Add Todo</div>
	</div>
	<div class="ui centered raised card" v-if="add">			
		<div class="ui content form">
			<div class="field">
				<label for="">Title</label>
				<input type="text" v-model="newTitle">
			</div>
			<div class="field">
				<label for="">Description</label>
				<input type="text" v-model="newDesc">
			</div>
			<div class="ui black button" @click="addTodo">Add Todo</div>
		</div>
	</div>
	<todo v-for='todo,index in todos' :todo="todo" v-on:delete-todo="deleteTodo"></todo>
	</div>
</template>

<script>

import Todo from './Todo'

	export default{
		props:["todos"],
		components:{Todo},
		methods:{
			deleteTodo(todo){
				this.todos.splice(this.todos.indexOf(todo),1);
			},
			addTodo(){
				console.log("works");
				var newTodo = {
					title:this.newTitle,
					desc:this.newDesc,
					done:false
				}
				this.todos.push(newTodo);
				this.newDesc='';
				this.newTitle='';
				this.add=false;
			}
		},
		data(){
			return{
				newTitle:"",
				newDesc:"",
				add:false
			}
		}
	};
</script>

<style>
	
</style>
