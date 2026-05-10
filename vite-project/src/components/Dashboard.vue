<template>
    <div class="main">
        <div class="header">
            <h1>控制台</h1>
            <p>校园门禁系统实时监控</p>
        </div>

        <div class="grid">
            <div class="base-info">
                <h1>注册人员</h1>
                <p>6</p>
                <p>1人已录入人脸</p>
            </div>
            <div class="base-info">
                <h1>注册人员</h1>
                <p>6</p>
                <p>1人已录入人脸</p>
            </div>
            <div class="base-info">
                <h1>注册人员</h1>
                <p>6</p>
                <p>1人已录入人脸</p>
            </div>
            <div class="base-info">
                <h1>注册人员</h1>
                <p>6</p>
                <p>1人已录入人脸</p>
            </div>
        </div>


    </div>
</template>

<script setup>
</script>

<style lang="scss" scoped>
@mixin h1($font-weight: bold, $font-size: 1.5rem) {
    font-weight: $font-weight;
    font-size: $font-size;
    font-style: italic;
    margin: 0;
}

.main {
    display: flex;
    flex-direction: column;
    padding: 10px;
    padding-right: 50px;

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
        justify-content: space-between;

        width: 100%;
        margin: 0;
        padding: 10px;

        .base-info {
            border-radius: 10px;
            border: 1px solid black;

            h1 {
                @include h1(normal, 0.75rem);
            }
        }
    }
}
</style>