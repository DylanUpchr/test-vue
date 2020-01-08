<template>
    <span>
        <input v-on:click="checkboxChange" ref="chk" type="checkbox" :checked=this.Item.checked >
        <span v-bind:class="{ striked: this.Item.checked }">{{ Item.name }}</span>
        <font-awesome-icon v-on:click="$emit('delete-item', Item.uuid)" icon="trash-alt" />
    </span>
</template>
<script>
export default {
    props:[
        'item'
    ],
    data: function(){
        
        return{
            Item: this.item
        }
    },
    methods:{
        checkboxChange(){
            this.Item.checked = this.$refs.chk.checked
            this.$emit('checked-item')
        }
    }
}
</script>
<style scoped>
    span{
        margin-left: 5px;
        margin-right: 5px;
    }
    .striked{
        text-decoration: line-through;
    }
</style>