<template>
  <div>
    <input type="text" placeholder="FirstName" v-model="name" >
    <input type="text" placeholder="LastName" v-model="lastNmame">
    <button @click="add">ADD</button>
  </div>
  <list-content :list="list" @removeList="remove  "></list-content>
</template>

<script>
import List from '../components/ListContent.vue'
  export default{
    components: {
      'list-content': List
    },
    data(){
      return{
        name: '',
        lastNmame: '',
        list: []
      }
    },
    methods: {
      add(){
        if (this.name.length && this.lastNmame.length) {
          this.list.push(`${this.name} - ${this.lastNmame}`)
          this.name = ''
          this.lastNmame = '' 
        }else{
          console.log('write something')
        }
      },
      remove(index) {
        this.list.splice(index, 1 )
      }
    }
  }
</script>


<style>
.content .list  p {
  margin-right: 10px;
}
.content .list {
  display: flex;
  align-items: center;
}



</style>

