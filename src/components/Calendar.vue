<template>
    <div style="padding: 0 70px">
        <div style="display: flex; flex-direction: row; justify-content: space-around">
            <calendar-month
                v-for="i in 3"
                :months-from-now="i - 1"
                :key="i"
            ></calendar-month>

        </div>

        <div style="margin: 40px 0; text-align: center">
            <a @click="page = page - 1" class="link"><b>&lt;</b></a>
            <a class="link">&bull;</a>
            <a @click="page = page + 1" class="link"><b>&gt;</b> </a>
        </div>

    </div>
</template>

<script>

    import CalendarMonth from "./CalendarMonth";
    export default {
        name: "Calendar",
        components: {CalendarMonth},
        data(){
            return {
                page: 1
            }
        },

        watch: {
            page(val){
                alert(val)
            }
        }
    }
</script>

<style scoped>
    .link{
        font-size: 20px;
        padding: 0 5px
    }
</style>