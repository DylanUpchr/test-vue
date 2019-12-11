<template>
    <div>
        Set a title and press Enter
        <input type="text" id="titleInput" v-on:change="$emit('title-change', $event.target.value)">
    </div>
</template>
<script>
export default {
    name: 'ListTitle'
}
</script>
<style scoped>

</style>