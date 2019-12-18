<template>
    <div>
        <div v-for="item in this.Items" :key="item.uuid">
            <item :item="item" v-on:delete-item="ReEmitDeleteItem"></item>
        </div>
    </div>
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
        }
    }
}
</script>
<style scoped>

</style>