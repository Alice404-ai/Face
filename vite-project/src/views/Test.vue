<template>
    <button @click="test" class="button">测试</button>
</template>

<script setup> 
import api from '../api/api'

async function test() {
    const response = await api.get('');
    const data = response.data;
    console.log(response);
    console.log(data);
}
</script>

<style lang="scss" scoped>
.button {
    width: 160px;
    height: 160px;
}
</style>