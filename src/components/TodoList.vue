<template>
  <div class="todoListWrap">
    <ul class="todoList">
      <li class="todoItem" v-for= "(todoItem, index) in propsdata" :key="todoItem">
        <span class="todoItemOrder">-</span>
        <span class="todoItemData">{{todoItem}}</span>
        <button class="btnTodoItemDelet" type="button" @click="removeTodo(todoItem, index)">삭제</button>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  props:['propsdata'],

  methods: {
    removeTodo(todoItem,index){
      this.$emit('removeTodo', todoItem, index);
      // localStorage.removeItem(todoItem);
      // this.todoItems.splice(index,1);
    }
  }
}
</script>
