<template>
    <nav>
        <div class="viewMode">
            <div class="expert bg-w">
                <div>Эксперт</div>
                <img src="../assets/img/arrow.svg" alt="arrow">
            </div>
            <div class="icon">
                <img src="../assets/img/bred.svg" alt="">
            </div>
        </div>
        <div class="menu bg-w">
            <div class="menu__item" v-for="item in menu" :key="item.title">
                <img :src="require(`../assets/img/${item.img}`)">
                <div class="title">{{item.title}}</div>
            </div>
        </div>

    </nav>
</template>

<script>
    export default {
        name: "SideBar",
        data: () => ({
            menu: [
                {img: 'analytics.svg', title: 'Аналитика'},
                {img: 'prod.svg', title: 'Продукт'},
                {img: 'users.svg', title: 'Пользователи', isActive: true},
                {img: 'constructor.svg', title: 'Констурктор сайта'},
                {img: 'translation.svg', title: 'Трансляции'},
                {img: 'mailing.svg', title: 'Рассылка'},
                {img: 'marketing.svg', title: 'Маркетинг'},
                {img: 'payment.svg', title: 'Платежи'},
                {img: 'customization.svg', title: 'Настройки'},
            ]
        }),
    }

</script>

<style scoped lang="scss">

    nav {
        font-family: 'PT Sans', sans-serif;
        font-weight: bold;
        margin-right: 104px;

        .viewMode {
            display: flex;
            position: relative;
            margin-bottom: 11px;

            .expert {
                display: flex;
                align-items: center;
                padding: 18px 23px 17px 20px;
                border-radius: 10px;

                position: absolute;
                z-index: 2;

                div {
                    margin-right: 67px;
                }
            }

            .icon {
                border-radius: 10px;
                padding: 14px 19px 13px 81px;
                background-color: #FAFBFC;
                margin-left: 112px;
            }
        }

        .menu {
            padding: 9px 0 9px 0;
            border-radius: 10px;
            width: 177px;

            &__item {
                border: 1px solid #E7ECF1;
                box-sizing: border-box;
                border-radius: 6px;
                text-align: center;
                margin-bottom: 8px;
                padding: 19px 0 11px;
                margin: 0 9px 8px 10px;
            }
        }
    }
</style>