<template>
    <div>
        <div class="modalContainer" v-show="modalIsOpen">
            <div class="overlay" @click="modalIsOpen = !modalIsOpen">
                <div class="filters">
                    <div class="selectDate bg-w">
                        <div class="date" v-for="date in dates" :key="date">{{date}}</div>
                    </div>
                    <div class="calendar bg-w">
                        <DatePicker is-range color="orange" v-model="range" :model-config="modelConfig"/>
                        <div class="calendar__actions">
                            <div class="cancel">
                                <button>Отмена</button>
                            </div>
                            <div class="refresh">
                                <button>Обновить</button>
                            </div>
                        </div>

                    </div>
                </div>

            </div>
        </div>


        <div class="pageHeader bg-w">
            <div class="filters" @click="modalIsOpen = !modalIsOpen">
                <div class="templates">
                    <img src="../assets/img/calendar.svg" alt="">
                    <div class="text">За 1 день</div>
                    <img src="../assets/img/arrow.svg" alt="">
                </div>
                <div class="filter">
                    <img src="../assets/img/filter.svg" alt="">
                    <div class="text">Фильтр</div>
                    <img src="../assets/img/arrow.svg" alt="">
                </div>
            </div>
            <div class="actions">
                <div class="unload">
                    <button class="bg-w">Выгрузить</button>
                </div>
                <div class="addContact">
                    <button>Добавить контакты</button>
                </div>
            </div>
        </div>
        <div class="users bg-w">
            <div class="users__header">
                <input type="checkbox" v-model="selectUsers" @change="selectAll">
                <div>Пользователь</div>
                <div>Дата регистрации</div>
                <div>Последняя активность</div>
                <div>Последнее действие</div>
                <div>Продукт</div>
                <div class="options">
                    <div>Отобразить</div>
                    <div>15</div>
                    <img src="../assets/img/arrow.svg" alt="arrow">
                </div>
            </div>
            <div class="users__body" v-for="user in users" :key="user.name">
                <input type="checkbox" v-model="user.checked">
                <div class="users__body_info" @click="user.active = !user.active"
                     :class="user.active || user.checked ? 'userActive' : ''  ">
                    <div>
                        <div class="userName">{{user.name}}</div>
                        <div class="userEmail">{{user.email}}</div>
                    </div>
                    <div class="date">{{new Date(user.dateRegister) | moment(" MMMM DD, YYYY") }}</div>
                    <div class="date">{{new Date(user.lastActive) | moment(" MMMM DD, YYYY") }}</div>
                    <div class="lastAction">{{user.lastAction}}</div>
                    <div class="product">{{user.product}}</div>
                </div>
                <div class="options">
                    <img src="../assets/img/edit.svg" alt="">
                    <img src="../assets/img/basket.svg" alt="">
                </div>
            </div>
        </div>
    </div>

</template>

<script>


    import DatePicker from 'v-calendar/lib/components/date-picker.umd'

    export default {
        name: "Users",
        components: {DatePicker},
        data: () => ({
            users: [
                {
                    checked: false,
                    name: 'User1',
                    email: 'user@user.com',
                    dateRegister: 1613814842739,
                    lastActive: 1613814842739,
                    lastAction: 'view_landing_course1',
                    product: 'Как наладить отнош',
                    active: false
                },
                {
                    checked: false,
                    name: 'User2',
                    email: 'user@user.com',
                    dateRegister: 1621063905167,
                    lastActive: 1613814842739,
                    lastAction: 'view_landing_course1',
                    product: 'Как наладить отнош',
                    active: false
                },
                {
                    checked: false,
                    name: 'User3',
                    email: 'user@user.com',
                    dateRegister: 1621063905167,
                    lastActive: 1621063905167,
                    lastAction: 'view_landing_course1',
                    product: 'Как наладить отнош',
                    active: false
                },
                {
                    checked: false,
                    name: 'User4',
                    email: 'user@user.com',
                    dateRegister: 1613814842739,
                    lastActive: 1621063905167,
                    lastAction: 'view_landing_course1',
                    product: 'Как наладить отнош',
                    active: false
                },
                {
                    checked: false,
                    name: 'User5',
                    email: 'user@user.com',
                    dateRegister: 1621063905167,
                    lastActive: 1621063905167,
                    lastAction: 'view_landing_course1',
                    product: 'Как наладить отнош',
                    active: false
                },
                {
                    checked: false,
                    name: 'User6',
                    email: 'user@user.com',
                    dateRegister: 1621063905167,
                    lastActive: 1621063905167,
                    lastAction: 'view_landing_course1',
                    product: 'Как наладить отнош',
                    active: false
                },
                {
                    checked: false,
                    name: 'User7',
                    email: 'user@user.com',
                    dateRegister: 1621063905167,
                    lastActive: 1621063905167,
                    lastAction: 'view_landing_course1',
                    product: 'Как наладить отнош',
                    closed: true,
                    active: false
                },
                {
                    checked: false,
                    name: 'User8',
                    email: 'user@user.com',
                    dateRegister: 1621063905167,
                    lastActive: 1621063905167,
                    lastAction: 'view_landing_course1',
                    product: 'Как наладить отнош',
                    active: false
                },
                {
                    checked: false,
                    name: 'User9',
                    email: 'user@user.com',
                    dateRegister: 1621063905167,
                    lastActive: 1621063905167,
                    lastAction: 'view_landing_course1',
                    product: 'Как наладить отнош',
                    active: false
                },
                {
                    checked: false,
                    name: 'User10',
                    email: 'user@user.com',
                    dateRegister: 1621063905167,
                    lastActive: 1621063905167,
                    lastAction: 'view_landing_course1',
                    product: 'Как наладить отнош',
                    active: false
                },
                {
                    checked: false,
                    name: 'User11',
                    email: 'nataha91@natasha.com',
                    dateRegister: 1621063905167,
                    lastActive: 1621063905167,
                    lastAction: 'view_landing_course1',
                    product: 'Как наладить отнош',
                    active: false
                },
                {
                    checked: false,
                    name: 'User12',
                    email: 'nataha91@natasha.com',
                    dateRegister: 1621063905167,
                    lastActive: 1621063905167,
                    lastAction: 'view_landing_course1',
                    product: 'Как наладить отнош',
                    active: false
                },
                {
                    checked: false,
                    name: 'User13',
                    email: 'nataha91@natasha.com',
                    dateRegister: 1621063905167,
                    lastActive: 1621063905167,
                    lastAction: 'view_landing_course1',
                    product: 'Как наладить отнош',
                    active: false
                },
                {
                    checked: false,
                    name: 'User14',
                    email: 'nataha91@natasha.com',
                    dateRegister: 1621063905167,
                    lastActive: 1621063905167,
                    lastAction: 'view_landing_course1',
                    product: 'Как наладить отнош',
                    active: false
                },
            ],
            modalIsOpen: false,
            selectUsers: false,
            range: {
                start: "",
                end: new Date(),
            },
            modelConfig: {
                type: 'number',
            },
            dates: ['Весь срок', 'Сегодня', 'Вчера', 'Последние 7 дней', 'Последние 30 дней', 'В этом месяце', 'Прошлый месяц'],
            options: {
                year: 'numeric',
                month: 'long',
                day: 'numeric',
            },

        }),
        methods: {
            selectAll: function () {
                this.users.forEach((item) => {
                    if (this.selectUsers === true) {
                        item.checked = false
                        item.checked = true
                    } else {
                        item.checked = false
                    }
                })
            },
        },
        computed: {
            rangeDate: function () {
                return this.range.start.toLocaleString("ru", this.options)
            },

        }
    }
</script>

<style lang="scss">
    .modalContainer {
        position: relative;

        .overlay {
            position: fixed;
            left: 0;
            top: 0;
            width: 100vw;
            height: 100vh;
            background: rgba(240, 246, 252, 0.7);
            z-index: 999;

            .filters {
                display: flex;
                position: absolute;
                left: 343px;
                top: 171px;
                overflow-scrolling: initial;

                .selectDate {
                    padding: 10px 10px 45px;
                    margin-right: 8px;
                    border-radius: 10px;

                    .date {
                        font-family: 'PT Sans', sans-serif;
                        font-size: 15px;
                        font-weight: normal;
                        width: 154px;
                        height: 39px;
                        line-height: 39px;
                        padding-left: 14px;

                        &:hover {
                            border: 2px solid #EBEEF3;
                            border-radius: 5px;
                        }
                    }
                }

                .calendar {

                    .vc-container {
                        border: none;
                        width: 100%;

                        .vc-day-content {
                            width: 28px;
                            height: 28px;

                            &:hover {
                                background: #DFE9F3;
                            }
                        }

                        .vc-weeks {
                            background: #F3F8FD;
                        }

                    }

                    &__actions {
                        display: flex;
                        margin: 10px;


                        .cancel {
                            margin-right: 7px;

                            button {
                                font-weight: 600;
                                font-size: 12px;
                                width: 130px;
                                height: 45px;
                                border: 2px solid #000000;
                                box-sizing: border-box;
                                border-radius: 7px;
                                text-align: center;
                                line-height: 40px;
                            }

                        }

                        .refresh {
                            button {
                                width: 130px;
                                height: 45px;
                                background: rgba(255, 116, 57, 0.5);
                                border-radius: 7px;
                                color: white;
                                font-weight: 600;
                                font-size: 12px;
                                text-align: center;
                                line-height: 40px;
                            }
                        }
                    }
                }
            }
        }

    }

    .pageHeader {
        display: flex;
        justify-content: space-between;
        margin-bottom: 10px;
        padding: 20px 20px 20px 35px;
        align-items: center;

        .filters {
            display: flex;
            align-items: center;
            font-weight: 500;
            font-size: 15px;

            .templates {
                display: flex;
                align-items: center;
                margin-right: 44px;
            }

            .filter {
                display: flex;
                align-items: center;
            }

            .text {
                margin-left: 20px;
                margin-right: 8px;
            }
        }

        .actions {
            display: flex;
            align-items: center;


            .unload {
                margin-right: 11px;

                button {
                    border: 2px solid #000000;
                    box-sizing: border-box;
                    border-radius: 7px;
                    width: 120px;
                    height: 45px;
                    font-size: 14px;
                    font-weight: bold;
                }
            }

            .addContact button {
                width: 199px;
                height: 45px;
                background: #FF7439;
                border-radius: 7px;
                font-size: 14px;
                font-weight: bold;
                color: white;
                border: none;
            }
        }
    }

    .users {
        width: 1269px;
        border-radius: 10px;
        font-weight: bold;
        font-size: 15px;

        &__header {
            display: grid;
            grid-template-columns: 64px 1fr 1fr 1fr 1fr 1fr 150px;
            align-items: center;
            height: 62px;
            border-bottom: 1px solid #E7ECF1;
            margin-left: 32px;
            margin-right: 43px;

            .options {
                display: flex;
                align-items: center;
                justify-content: flex-end;
                font-weight: normal;
                font-size: 13px;

                * + * {
                    margin-left: 11px;
                }
            }
        }

        &__body {
            display: grid;
            grid-template-columns: 64px 1fr 150px;
            height: 62px;
            align-items: center;
            margin-left: 32px;
            margin-right: 43px;

            &_info {
                display: grid;
                grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
                align-items: center;
                padding-left: 16px;
            }

            .userActive {
                border: 2px solid #EBEEF3;
                border-radius: 5px;
            }

            .lastAction, .product {
                position: relative;

                &:after {
                    position: absolute;
                    left: 0;
                    height: 100%;
                    width: 100%;
                    content: "";
                    background: linear-gradient(to left,
                            rgba(255, 255, 255, 1) 20%,
                            rgba(255, 255, 255, 0) 80%
                    );
                    pointer-events: none;
                }
            }

            .options {
                text-align: right;

                img + img {
                    margin-left: 39px;
                }
            }

            .userEmail {
                font-weight: normal;
                font-size: 13px;
                line-height: 130%;
                margin-top: 7px;
            }

            .date {
                text-transform: capitalize;
            }
        }
    }

    .vc-day {

    }
</style>