<template>
    <aside class="aside">
        <header class="header">
            <div class="icon">
                <img src="../assets/shield-solid.png" alt="Logo" />
            </div>
            <div class="title">
                <p>智慧校园</p>
                <p>人脸识别门禁系统</p>
            </div>
        </header>
        
        <nav>
            <ul>
                <li 
                    v-for="(item, index) in menu" 
                    :key="index"
                    :class="{ active: activeIndex === index}"
                    @click="select(index)"
                >
                    <img src="../assets/vue.svg" alt="Arrow" />
                    {{  item  }}
                </li>
            </ul>
        </nav>

        <footer class="footer">
            <div class="system-status">
                <li>系统运行中</li>
                <p>所有门禁设备在线</p>
            </div>
        </footer>
    </aside>
</template>

<script setup>
import { ref, defineEmits } from 'vue'

const menu = ['控制台', '人员管理', '门禁识别', '通行记录']
const activeIndex = ref(0)

const emit = defineEmits(['menu-selected'])

function select(index) {
    activeIndex.value = index
    emit('menu-selected', index)
}

</script>

<style lang="scss" scoped>
$font-family: "Helvetica Neue", Helvetica, Arial, "PingFang SC", "Microsoft YaHei", sans-serif;
$font-color: black;
$normal-font-size: 14px;
$active-color: #2463eb;
$hover-color: #f1f5f9;
$box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);

@mixin img($size: 40px) {
    width: $size;
    height: $size;
    object-fit: contain;
}

.aside {
    font-family: $font-family;
    width: 250px;
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
            font-weight: bold;
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
                border-radius: 5px;
                padding: 5px;
                cursor: pointer;
                display: flex;
                align-items: center;
                padding: 5px;
                gap: 5px;

                &:hover {
                    background-color: $hover-color;
                    border-radius: 5px;
                    transition: background-color 0.3s ease;
                }

                &.active {
                    color: white;
                    background-color: $active-color;
                    border-radius: 5px;
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
        background-color: #d7d9da;
        border-radius: 0.75rem;
        box-shadow: $box-shadow;

        .system-status {
            display: flex;
            flex-direction: column;
            align-items: flex-start;

            &:only-child {
                margin-left: 20px;
            }

            li {
                list-style: none;
                font-size: $normal-font-size;
                color: $font-color;
                margin-bottom: 5px;
            }

            p {
                font-size: $normal-font-size;   
                color: $font-color;
            }
        }
    }
}
</style>