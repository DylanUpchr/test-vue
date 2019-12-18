<template>
    <div>
        <input ref="itemName" class="form-control" type="text" placeholder="add list item">
        <button type="submit" class="btn btn-primary" v-on:click="$emit('add-list-item', createItem())">Add</button>
        <span class="glyphicon glyphicon-trash"></span>
    </div>
</template>
<script>
const uuidv4 = require('uuid/v4');
export default {
    name: 'AddItem',
    methods:{
        createItem(){
            var item = {
                'uuid': uuidv4(),
                'name': this.$refs.itemName.value,
                'checked': false
            }
            return item;
        }
    }
}
</script>
<style scoped>
    input{
        width: auto;
        margin: auto;
        display: inline-block;
    }
    button{
        display: inline;
    }
</style>