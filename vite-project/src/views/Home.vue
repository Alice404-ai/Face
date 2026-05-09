<template>
    <div class="body">
        <Aside />
        
        <div class="mainContent">
            123
        </div>
    </div>
</template>


<script setup>
import Aside from '../components/Aside.vue';

</script>

<style lang="scss" scoped>

.body {
    display: flex;
    width: 100%;
    height: 100vh;

 
    .mainContent {
        flex: 1;
        padding: 20px;
        border: 1px solid #ccc;
        background-color: #f6f7f9;
    }
}
</style>