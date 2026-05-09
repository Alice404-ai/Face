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
                <li>
                   <router-link to="/" exact-active-class="active">控制台</router-link> 
                </li>
                <li>
                    <router-link to="/per" exact-active-class="active">人员管理</router-link>
                </li>
                <li>
                    <router-link to="/contact" exact-active-class="active">门禁识别</router-link>
                </li>
            </ul>
        </nav>
    </aside>
</template>

<script setup>
import router from '../router';

</script>

<style lang="scss" scoped>
$font-color: black;
$active-color: #2463eb;
$hover-color: #f1f5f9;

.aside {
    width: 250px;
    padding: 20px;
    
    .header {
        display: flex;

        .icon {
            width: 40px;
            height: 40px;
            margin: 5px;

            img {
                width: 100%;
                height: 100%;
                object-fit: contain;
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
                font-size: 12px;
                text-align: left;

                &:first-child {
                    font-weight: bold;
                    font-size: 16px;
                }
            }
        }
    }

    nav {
        display: flex;
        width: 100%;

        ul {
            list-style: none;
            width: 100%;
            padding: 0;

            li {
                width: 80%;
                margin-bottom: 10px;
                cursor: pointer;
                
                &:hover {
                    background-color: $hover-color;
                    border-radius: 5px;
                }

                &.active {
                    background-color: $active-color;
                    border-radius: 5px;
                }

                a {
                    cursor: pointer;
                    margin-left: 10px;
                    text-decoration: none;
                    color: $font-color;
                }
            }
        }
    }
}
</style>