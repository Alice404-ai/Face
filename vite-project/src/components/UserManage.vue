<template>
    <div class="main">
        <div class="header">
            <div class="info">
                <h1>人员管理</h1>
                <p>管理校园门禁授权人员及人脸信息</p>
            </div>
            <button class="add-new-info">
                + 添加人员
            </button>
        </div>
        <div class="search-box">
            <span class="icon">🔍</span>
            <input type="text" placeholder="搜索姓名、学号、部门..." />
        </div>

    </div>
</template>

<script setup>
</script>

<style lang="scss" scoped>
@mixin h1($font-weight: bold, $font-size: 1.5rem, $color: black, $letter-spacing: 2px) {
    letter-spacing: $letter-spacing;
    font-weight: $font-weight;
    font-size: $font-size;
    font-style: italic;
    color: $color;
    margin: 0;
}

@mixin p($font-size: 0.875rem) {
    font-size: $font-size;
}

.main {
    display: flex;
    flex-direction: column;
    padding: 10px;
    padding-right: 50px;
    gap: 20px;

    .header {
        display: flex;
        flex-direction: row;
        align-items: flex-start;
        justify-content: space-between;
        gap: 10px;
        width: 100%;
        padding: 10px;

        .info {
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            gap: 10px;

            h1 {
                @include h1(bold);
            }

            p {
                @include p;
            }
        }

        .add-new-info {
            cursor: pointer;
            font-size: 14px;
            gap: 20px;
            border-radius: 10px;
            padding: 8px 12px;
            width: 7%;
            color: white;
            background-color: rgb(36, 99, 235);
            border: none;
        }
    }

    .search-box {
        display: flex;

        input {
            border-radius: 10px;
        }
    }
}
</style>