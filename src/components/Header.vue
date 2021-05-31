<template>
    <header>
        <div class="logo">
            <img src="../assets/img/logo.png" alt="">
            <span>Beta</span>
        </div>
        <div class="menu">
            <div class="notification bg-w round">
                <img src="../assets/img/notification.png" alt="">
            </div>
            <div class="user bg-w">
                <div>Артем</div>
                <img src="../assets/img/arrow.svg" alt="arrow">
            </div>
            <div class="search bg-g round ">
                <img src="../assets/img/search.png" alt="">
            </div>
            <div class="lang bg-g">
                <div>Ru</div>
                <img src="../assets/img/arrow.svg" alt="arrow">
            </div>
        </div>
    </header>
</template>

<script>
    export default {
        name: "Header"
    }
</script>

<style scoped lang="scss">
    header {
        display: flex;
        justify-content: space-between;
        margin-bottom: 48px;

        .round {
            border-radius: 50%;
            text-align: center;
            width: 43px;
            height: 43px;
            line-height: 53px;
        }

        .logo {
            span {
                margin-left: 9px;
            }
        }

        .menu {
            display: flex;
            font-weight: bold;
            font-size: 14px;

            .notification {
                margin-right: 17px;
            }

            .user {
                display: flex;
                align-items: center;
                padding: 12px 18px 12px 26px;
                border-radius: 100px;
                margin-right: 17px;

                div {
                    margin-right: 15px;
                }
            }

            .search {
                margin-right: 17px;
            }

            .lang {
                display: flex;
                padding: 12px 18px 12px 26px;
                border-radius: 100px;
                align-items: center;

                div {
                    margin-right: 15px;
                }
            }
        }
    }
</style>