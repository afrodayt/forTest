<template>
    <div class="modal">
        <div class="selectDate">
            <div class="date" v-for="date in dates" :key="date">{{date}}</div>
        </div>
        <div class="calendar">
            <DatePicker is-range color="orange" v-model="range" :model-config="modelConfig"/>
        </div>


    </div>
</template>

<script>
    import DatePicker from 'v-calendar/lib/components/date-picker.umd'

    export default {
        name: "Filters",
        components: {
            DatePicker
        },
        data: () => ({
            dates: ['Весь срок', 'Сегодня', 'Вчера', 'Последние 7 дней', 'Последние 30 дней', 'В этом месяце', 'Прошлый месяц'],
            range: {
                start: new Date(),
                end: new Date(),
            },
            modelConfig: {
                type: 'number',
            },

        })
    }
</script>

<style scoped lang="scss">
    .modal {
        display: flex;
        position: relative;

        .selectDate {
            position: absolute;
        }

        .calendar {
            position: absolute;
            left: 100px;
        }
    }
</style>