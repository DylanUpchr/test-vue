<template>
    <span>
        <input v-on:click="checkboxChange" ref="chk" type="checkbox" :checked=this.Item.checked >
        <span v-bind:class="{ striked: this.Done }">{{ Item.name }}</span>
        <font-awesome-icon v-on:click="$emit('delete-item', Item.uuid)" icon="trash" />
    </span>
</template>
<script>
export default {
    props:[
        'item'
    ],
    data: function(){
        
        return{
            Item: this.item,
            Done: false
        }
    },
    methods:{
        checkboxChange(){
            this.Done = this.$refs.chk.checked
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