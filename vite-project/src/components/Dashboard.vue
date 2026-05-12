<template>
    <div class="main">
        <div class="header">
            <h1>控制台</h1>
            <p>校园门禁系统实时监控</p>
        </div>

        <div class="grid">
            <div class="base-info">
                <div class="info">
                    <h1>注册人员</h1>
                    <p>6</p>
                    <p>1人已录入人脸</p>
                </div>
                <div class="image">
                    <img src="../assets/icons/shield-solid.png">
                </div>
            </div>
            <div class="base-info">
                <div class="info">
                    <h1>注册人员</h1>
                    <p>6</p>
                    <p>1人已录入人脸</p>
                </div>
                <div class="image">
                    <img src="../assets/icons/shield-solid.png">
                </div>
            </div>
            <div class="base-info">
                <div class="info">
                    <h1>注册人员</h1>
                    <p>6</p>
                    <p>1人已录入人脸</p>
                </div>
                <div class="image">
                    <img src="../assets/icons/shield-solid.png">
                </div>
            </div>
            <div class="base-info">
                <div class="info">
                    <h1>注册人员</h1>
                    <p>6</p>
                    <p>1人已录入人脸</p>
                </div>
                <div class="image">
                    <img src="../assets/icons/shield-solid.png">
                </div>
            </div>
        </div>

        <div class="tables">
            <div class="pass-trend">
                <h1>今日通行趋势</h1>
                <Charts />
            </div>
            <div class="recently-pass-record">
                <h1>最近通行记录</h1>
                <ul>
                    <li>
                        <div>
                            123
                        </div>
                        <div class="content">
                            <P>123</P>
                            <p>123</p>
                        </div>
                        <div>123</div>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script setup>
import Charts from './Charts.vue';

</script>

<style lang="scss" scoped>
.main {
    display: flex;
    flex-direction: column;
    padding: 10px;
    padding-right: 50px;
    gap: 20px;

    .header {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        gap: 10px;
        width: 100%;
        padding: 10px;

        h1 {
            @include h1(bold);
        }

        p {
            @include p;
        }
    }

    .grid {
        display: flex;
        flex-direction: row;
        width: 100%;
        margin: 0;
        gap: 30px;

        .base-info {
            flex: 1;
            display: flex;
            flex-direction: row;
            border-radius: 10px;
            border: $normal-border;
            align-items: center;
            padding: 15px;
            justify-content: space-between;
            height: 100px;
            box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            background-color: white;

            &:hover {
                transition: scale(1.5);
                box-shadow: 0 3px 6px rgba(0, 0, 0, 0.3);
            }

            .info {
                display: flex;
                flex-direction: column;
                align-items: flex-start;

                h1 {
                    @include h1(normal, 0.9rem, $normal-font-color);
                    margin-bottom: 20px;
                }

                p {
                    font-size: 12px;

                    &:nth-child(2) {
                        font-weight: bold;
                        font-size: 28px;
                        color: $bold-font-color;
                    }
                }
            }

            .image {
                align-self: flex-start;

                img {
                    @include img;
                }
            }
        }
    }

    .tables {
        display: flex;
        flex-direction: row;
        gap: 1.875rem;

        .pass-trend {
            flex: 2;
            border: $normal-border;
            border-radius: $border-radius;
            background-color: white;
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            padding: 10px;
            padding-top: 20px;
            padding-left: 20px;

            h1 {
                @include h1(bold, 0.9rem);
            }
        }

        .recently-pass-record {
            flex: 1;
            padding: 20px;
            border: $normal-border;
            border-radius: $border-radius;
            height: 100px;
            background-color: white;
            display: flex;
            flex-direction: column;
            align-items: flex-start;

            h1 {
                @include h1(bold, 0.9rem);
            }

            ul {
                list-style: none;
                width: 100%;

                li {
                    display: flex;
                    flex-direction: row;
                    flex-wrap: nowrap;
                    justify-content: space-between;
                    align-items: center;
                    width: 80%;
                    border: $normal-border;
                    border-radius: $border-radius;

                    .content {
                        display: flex;
                        flex-direction: column;
                    }
                }
            }
        }
    }
}
</style>