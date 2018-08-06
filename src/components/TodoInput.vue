<template>
  <div class="inputWrap">
    <input type="text" class="inputTodo" v-model="newTodoItem" placeholder="Write Todo" v-on:keyup.enter= "addTodo">
    <button type="button" class="btnPlusTodo" v-on:click="addTodo">추가</button>
  </div>
</template>

<script>
export default {
  props:['propsdata'],
  data() {
    return {
      newTodoItem:''
    }
  },
  methods: {
    addTodo() {
      // localStorage.setItem(this.newTodoItem, this.newTodoItem);
      if(this.newTodoItem) {
        const value = this.newTodoItem && this.newTodoItem.trim();
        this.$emit('addTodo',value);
        // localStorage.setItem(value, value);
        // this.propsdata.push(value);
        this.clearInput();
      } else {
        console.log('test')
      }
    },
    clearInput() {
      this.newTodoItem = '';
    }
  }

}
</script>
