 
<template>
    <div class="week-list-contaier">
        <div class="title">
            HAFTALAR
        </div>
        <week-list
            :weeks = 'weeks'
            :currentWeek = 'currentWeek'
        ></week-list>
    </div>
</template>

<script>
import WeekList from './WeekList'; 

export default {
    data(){
        return {
            weeks : this.prepareWeekData(),
            currentWeek: this.findCurrentWeek()
        }
    },
    methods: {
        prepareWeekData (){
            var year = new Date().getFullYear();
            var currentWeek = this.findCurrentWeek();
            return [ ...Array(52).keys() ].map( i => { 
                return { 
                    weekNum: i+1, 
                    year: year,
                    weekText: `${i +1}. HAFTA ${year}`,
                    status: i + 1 == currentWeek ? 'current': i+1 > currentWeek ? 'future' : 'passed'
                } 
            })
        },
        findCurrentWeek(){
            var today = new Date()
            var dt = new Date( today.getFullYear(),0,1);
            return Math.ceil((((today - dt) / 86400000) + dt.getDay()+1)/7);
        }
    },
    components: {
        WeekList
    }
}
</script>

<style>
.week-list-contaier{
    width: 300px;
    color: gray;
    margin-left: 50px;
    border: 1px solid gray;
}
.week-list-contaier .title{
    position: relative;
    text-align: left;
    padding : 15px 0 15px 15px;
    border-bottom: 1px solid gray;
    font-size: 12px;
    font-weight: 700;
    background-color: lightgray
}
.week-list-contaier .title::before{
        content:'';
        width: 2px;
        height: 16px;
        background-color: gray;
        position: absolute;
        left: 10px;
}
.week-list-contaier ul{
        list-style: none;
}
</style>