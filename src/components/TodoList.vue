<template>
	<div>
	<div class="ui center aligned segment">
		<h3>Completed Tasks - {{todos.filter(todo=>todo.done).length}}</h3>
		<h3>Pending Tasks - {{todos.filter(todo=>!todo.done).length}}</h3>
	</div>
	<todo v-for='todo,index in todos' :todo="todo" ></todo>
	</div>
</template>

<script>

import Todo from './Todo'

	export default{
		props:["todos"],
		components:{Todo}
	};
</script>

<style>
	
</style>
