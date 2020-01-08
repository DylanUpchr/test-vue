<template>
    <ul>
        <li v-for="item in this.Items" :key="item.uuid">
            <item :item="item" v-on:delete-item="ReEmitDeleteItem" v-on:checked-item="ReEmitCheckedItem"></item>
        </li>
    </ul>
</template>
<script>
import Item from './Item.vue'
export default {
    name: 'ItemList',
    components: {'item': Item},
    props:[
        'items'
    ],
    data: function(){
        return{
            Items: this.items
        }
    },
    methods: {
        ReEmitDeleteItem(uuid){
           this.$emit('delete-item', uuid) 
        },
        ReEmitCheckedItem(){
           this.$emit('checked-item') 
        }
    }
}
</script>
<style scoped>
    ul{
        list-style: none;
    }
</style>