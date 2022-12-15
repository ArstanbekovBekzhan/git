<template>
    <div class="content" v-if="list.length">
        <div class="list" v-for="item, i in list">
        <p v-text="item" /><button @click="remove(i)">delete</button>
        </div>
  </div>
</template>


<script>
export default {
    props: {
        list:{
            type: Array,
            default:[]   
        }
    },
    methods: {
        remove(index) {
            this.$emit( 'removeList', index )
        }
    }
}
</script>