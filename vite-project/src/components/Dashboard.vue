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
                    <img src="../assets/shield-solid.png" >
                </div>
            </div>
            <div class="base-info">
                <div class="info">
                    <h1>注册人员</h1>
                    <p>6</p>
                    <p>1人已录入人脸</p>
                </div>
                <div class="image">
                    <img src="../assets/shield-solid.png" >
                </div>
            </div>
            <div class="base-info">
                <div class="info">
                    <h1>注册人员</h1>
                    <p>6</p>
                    <p>1人已录入人脸</p>
                </div>
                <div class="image">
                    <img src="../assets/shield-solid.png" >
                </div>
            </div>
            <div class="base-info">
                <div class="info">
                    <h1>注册人员</h1>
                    <p>6</p>
                    <p>1人已录入人脸</p>
                </div>
                <div class="image">
                    <img src="../assets/shield-solid.png" >
                </div>
            </div>
        </div>

        <div class="tables">
            <div class="pass-trend">
                <h1>今日通行趋势</h1>
                <div class="chart">
                    <Charts />
                </div>
            </div>
            <div class="recently-pass-record">

            </div>
        </div>
    </div>
</template>

<script setup>
import Charts from './Charts.vue';

</script>

<style lang="scss" scoped>
$normal-font-color: #65758b;
$bold-font-color: black;


@mixin h1($font-weight: bold, $font-size: 1.5rem, $color: black) {
    font-weight: $font-weight;
    font-size: $font-size;
    font-style: italic;
    color: $color;
    margin: 0;
}

@mixin img($size: 40px) {
    width: $size;
    height: $size;
    object-fit: contain;
}

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
            font-size: 0.875rem;
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
            border: 0.5px solid rgb(154, 154, 154);
            align-items: center;
            padding: 15px;
            justify-content: space-between;
            height: 100px;
            box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;

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
            border: 2px solid black;
            border-radius: 0.75rem;
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            padding: 10px;
            padding-top: 20px;

            h1 {
                @include h1(bold, 0.9rem);
                letter-spacing: 2px;
            }

            .chart {
                flex: 1;
                min-height: 400px;
            }
        }

        .recently-pass-record {
            flex: 1;
            border: 2px solid black;
            border-radius: 0.75rem;
            height: 100px;
        }
    }
}
</style>