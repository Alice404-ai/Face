<template>
    <div class="main">
        <div class="header">
            <div class="headInfo">
                <h1>人员管理</h1>
                <p>管理校园门禁授权人员及人脸信息</p>
            </div>
            <button class="add-new-info">
                + 添加人员
            </button>
        </div>
        <div class="search-box">
            <img src="../assets/icons/search.png" class="icon" alt="搜索按钮" />
            <input type="text" placeholder="搜索姓名、学号、部门..." />
        </div>
        <div class="table-wrapper">
            <table class="table">
                <thead>
                    <tr>
                        <th>人员信息</th>
                        <th>学号/工号</th>
                        <th>角色</th>
                        <th>部门</th>
                        <th>人脸状态</th>
                        <th>状态</th>
                        <th>操作</th>
                    </tr>
                </thead>

                <tbody>
                    <tr v-for="item in personList" :key="item.id">
                        <td>
                            <div class="person-info">
                                <div class="avatar">{{ item.name.charAt(0) }}</div>
                                <span class="name">{{ item.name }}</span>
                            </div>
                        </td>
                        <td>
                            <div class="info">{{ item.id }}</div>
                        </td>
                        <td>
                            <div class="status role">{{ item.role }}</div>
                        </td>
                        <td>
                            <div class="info">{{ item.department }}</div>
                        </td>
                        <td>
                            <div class="status face">{{ item.faceStatus }}</div>
                        </td>
                        <td>
                            <div class="status">{{ item.status }}</div>
                        </td>
                        <td>
                            <div class="opration">
                                <img src="../assets/icons/face-id.png" class="image" />
                                <img src="../assets/icons/trash-can-solid.png" class="image" />
                                
                                <!-- <div class="add-face"></div>
                                <div class="delete"></div> -->
                            </div>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</template>

<script setup>
const personList = [
    {
        name: "张三",
        id: "20231110001",
        role: "学生",
        department: "计算机学院",
        faceStatus: "已录入",
        status: "正常"
    },
    {
        name: "张三",
        id: "20231110001",
        role: "学生",
        department: "计算机学院",
        faceStatus: "已录入",
        status: "正常"
    },
    {
        name: "张三",
        id: "20231110001",
        role: "学生",
        department: "计算机学院",
        faceStatus: "已录入",
        status: "正常"
    },
]

function addFace() {
    alert('添加脸部照片');
}

function Delete() {
    alert('删除');
}
</script>

<style lang="scss" scoped>
$normal-font-color: #65758b;
$bold-font-color: black;
$normal-border: 0.5px solid rgb(154, 154, 154);
$border-radius: 0.75rem;
$status-color: rgb(15, 23, 41);

@mixin img($size: 40px) {
    width: $size;
    height: $size;
    object-fit: contain;
}


.main {
    line-height: 1.5rem;
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

        .headInfo {
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
            font-size:  $normal-font-size;
            gap: 1.25rem;
            border-radius: 10px;
            padding: 8px 12px;
            width: 7.5rem;
            color: white;
            background-color: rgb(36, 99, 235);
            border: none;
        }
    }

    .search-box {
        position: relative;
        display: flex;
        width: 400px;

        .icon {
            width: 16px;
            height: 16px;
            position: absolute;
            left: 12px;
            top: 50%;
            transform: translateY(-50%);
            color: #999;
            font-size: 14px;
        }

        input {
            background-color: #f6f7f9;
            width: 100%;
            padding: 10px 10px 10px 36px;
            border-radius: 8px;
            border: 1px solid #ddd;
            outline: none;

            &:focus {
                border: 1px solid #2463eb;
            }
        }
    }

    .table-wrapper {
        overflow: hidden;
        border-radius: 10px;
        border: 1px solid black;

        .table {
            width: 100%;
            border-collapse: collapse;

            thead {
                background-color: #f6f7f9;
                font-size: 12px;

                tr {

                    th {
                        text-align: left;
                        padding: $table-padding;

                        &:last-child {
                            text-align: right;
                        }
                    }
                }
            }

            tbody {
                background-color: white;

                tr {
                    border-bottom: 0.5px solid black;

                    &:hover {}

                    &:first-child {
                        border-top: 0.5px solid black;
                    }

                    &:last-child {
                        border-bottom: none;
                    }

                    td {
                        text-align: left;
                        padding: $small-table-padding;
                        border: none;

                        .person-info {
                            display: flex;
                            align-items: center;
                            gap: 12px;

                            .avatar {
                                width: 36px;
                                height: 36px;
                                border-radius: 50%;
                                background-color: rgba(36, 99, 235, 0.1);
                                color: rgba(36, 99, 235);
                                display: flex;
                                align-items: center;
                                justify-content: center;
                                font-size: 14px;
                                font-weight: bold;
                                flex-shrink: 0;
                            }

                            .name {
                                font-size: 14px;
                            }
                        }

                        .info {
                            font-size: 14px;
                            color: rgb(101, 117, 139);
                        }

                        .status {
                            font-family: 'Noto Sans SC Bold';
                            display: inline-flex;
                            padding: 2px 10px;
                            border-radius: 20px;
                            text-align: center;
                            font-size: 12px;
                            background-color: rgb(241, 245, 249);
                            border: 1px;
                            font-weight: 700;
                            color: green;
                        }
                        .status.role {
                            color: $status-color;
                        }
                        .status.face {
                            color: green;
                        }

                        .opration {
                            text-align: right;
                            .image {
                                cursor: pointer;
                                @include img(calc($icon-size / 2));
                            }
                        }
                    }
                }
            }
        }
    }
}
</style>