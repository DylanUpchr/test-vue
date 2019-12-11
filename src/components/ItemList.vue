<template>
    <div>
        <div v-for="item in this.Items" :key="item.uuid">
            <input type="checkbox" :checked=item.checked>
            <span v-bind:class="{ striked: item.checked}">{{ item.name }}</span>
        </div>
    </div>
</template>
<script>
export default {
    name: 'ItemList',
    props:[
        'items'
    ],
    data: function(){
        return{
            Items: this.items
        }
    }
}
</script>
<style scoped>
    span{
        margin-left: 5px;
    }
    .striked{
        text-decoration: line-through;
    }
</style>