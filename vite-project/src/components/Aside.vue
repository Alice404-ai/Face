<template>
    <aside class="aside">
        <header class="header">
            <div class="icon">
                <img src="../assets/icons/shield-solid.png" alt="Logo" />
            </div>
            <div class="title">
                <p>智慧校园</p>
                <p>人脸识别门禁系统</p>
            </div>
        </header>

        <nav>
            <ul>
                <li v-for="(item, index) in menu" :key="index" :class="{ active: activeIndex === index }"
                    @click="select(index)">
                    <img src="../assets/icons/vue.svg" alt="Arrow" />
                    {{ item }}
                </li>
            </ul>
        </nav>

        <footer class="footer">
            <div class="system-status">
                <p>系统正常运行中</p>
                <p>所有门禁设备在线</p>
            </div>
        </footer>
    </aside>
</template>

<script setup>
import { ref } from 'vue'

const menu = ['控制台', '人员管理', '门禁识别', '通行记录']
const activeIndex = ref(0)

const emit = defineEmits(['menu-selected'])

function select(index) {
    activeIndex.value = index
    emit('menu-selected', index)
}

</script>

<style lang="scss" scoped>

$font-family: "Noto Sans SC";
$font-color: black;
$hover-color: #f1f5f9;
$border-radius: 0.75rem;
$normal-font-size: 0.875rem;
$small-font-size: 0.625rem;
$box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);

@mixin img($size: 40px) {
    width: $size;
    height: $size;
    object-fit: contain;
}

.aside {
    font-family: $font-family;
    width: 220px;
    padding: 20px;
    display: flex;
    flex-direction: column;
    align-items: left;


    .header {
        display: flex;

        .icon {
            width: 40px;
            height: 40px;
            margin: 5px;

            img {
                @include img(40px);
            }
        }

        .title {
            font-size: 24px;
            display: flex;
            flex-direction: column;
            justify-content: center;

            p {
                color: $font-color;
                font-size: $normal-font-size;
                text-align: left;

                &:first-child {
                    font-weight: bold;
                    font-size: 16px;
                }
            }
        }
    }

    nav {
        width: 100%;

        ul {
            width: 100%;
            padding: 0;
            list-style: none;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 15px;

            li {
                font-size: $normal-font-size;
                width: 100%;
                height: 30px;
                padding: 5px;
                cursor: pointer;
                display: flex;
                align-items: center;
                padding: 5px;
                gap: 10px;

                &:hover {
                    background-color: $hover-color;
                    border-radius: $border-radius;
                    transition: background-color 0.3s ease;
                }

                &.active {
                    color: white;
                    background-color: $active-color;
                    border-radius: $border-radius;
                }

                img {
                    @include img(16px);
                    margin-left: 10px;
                }
            }
        }
    }

    .footer {
        align-self: center;
        margin-top: auto;
        width: 100%;
        padding: 10px;
        background-color: #fcf7f7;
        border-radius: $border-radius;
        box-shadow: $box-shadow;

        .system-status {
            display: flex;
            flex-direction: column;
            align-items: flex-start;

            &:only-child {
                margin-left: 20px;
            }

            p {
                font-size: $small-font-size;
                color: $font-color;
            }
        }
    }
}
</style>