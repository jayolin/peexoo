<template>
    <div>

        <div style="text-align: center">{{monthName}}</div>
        <ul class="ul">
            <li class="item-class" v-for="(dayOfTheWeek, k) in daysOfTheWeek" :key="`dayOfTheWeek-${k}`">
                <b>{{dayOfTheWeek}}</b>
            </li>
        </ul>
        <ul class="ul" v-for="(daysArray, i) in weeks" :key="i">
            <li
                :class="['item-class',
                        {'active-class': dateObject.date === currentDate && dateObject.month === currentMonth && dateObject.year === currentYear}
                        ]"
                v-for="(dateObject, j) in daysArray"
                :key="i + j"
            >
                <div v-if="dateObject.month === monthDigit">{{dateObject.date}}</div>
                <div v-else style="color: #bbb">{{dateObject.date}}</div>
            </li>
        </ul>
    </div>
</template>

<script>
    import moment from 'moment'
    export default {
        name: "CalendarMonth",
        props: {
            monthsFromNow: {
                type: Number,
                default: 0
            }
        },
        data(){
            return {
                weeks: [],
                daysOfTheWeek: ['Su', 'Mo', 'Tu', 'We', 'Th', 'Fr', 'Sa'],
                monthName: moment().add(this.monthsFromNow, 'months').format('MMMM'),
                monthDigit: moment().add(this.monthsFromNow, 'months').month(),

                currentMonth: moment().month(),
                currentDate: moment().add(this.monthsFromNow, 'months').date(),
                currentYear: moment().year()
            }
        },

        created(){

            //let month = moment().subtract(this.monthsFromNow, 'months').month();
            let startOfMonth = moment().add(this.monthsFromNow, 'months').startOf('month');
            let endOfMonth = moment().add(this.monthsFromNow, 'months').endOf('month');
            let startOfWeekOfTheMonth = startOfMonth.startOf('week');
            let endOfWeekOfMonth = endOfMonth.endOf('week');


            let daysToDisplay = Math.ceil(moment.duration(endOfWeekOfMonth.diff(startOfWeekOfTheMonth)).as('days'));

            for(let day = 1; day <= daysToDisplay; day++){

                let date = moment(startOfWeekOfTheMonth).add(day, 'day').date();
                let month = moment(startOfWeekOfTheMonth).add(day, 'day').month();
                let year = moment(startOfWeekOfTheMonth).add(day, 'day').year();

                let dayOfTheWeek = moment(startOfWeekOfTheMonth).add(day, 'day').days();
                let dateObject = {
                    date,
                    month,
                    year
                };
                if(dayOfTheWeek === 1){
                    this.weeks[this.weeks.length] = [dateObject];
                }
                else{
                    this.weeks[this.weeks.length - 1].push(dateObject)
                }

            }
        },
    }
</script>

<style scoped>
    .item-class{
        width: 34px;
        height: 34px;
        display: inline-block;
        text-align: center;
        line-height: 34px;
        margin: 0 5px
    }
    .ul{
        padding: 0;
        margin: 7px 0
    }
    .active-class{
        background: orange;
        color: #FFFFFF;
        border-radius: 50%;
    }
</style>