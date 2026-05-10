<template>
    <div class="body">
        <Aside @menu-selected="activeIndex = $event" />

        <div class="mainContent">
            <component :is="currentComponent"></component>
        </div>
    </div>
</template>


<script setup>
import { computed, ref } from 'vue';
import Aside from '../components/Aside.vue';
import Dashboard from '../components/Dashboard.vue'
import UserManage from '../components/UserManage.vue'
import FaceRecognition from '../components/FaceRecognition.vue';
import PassRecord from '../components/PassRecord.vue'

const activeIndex = ref(0)
const components = [Dashboard, UserManage, FaceRecognition, PassRecord]
const currentComponent = computed(() => components[activeIndex.value])
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
        overflow-y: auto;
        height: 100%;
        box-sizing: border-box;
    }
}
</style>