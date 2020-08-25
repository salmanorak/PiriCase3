<template>
    <div class="week-list">
        <ul >
            <week-list-item
                v-for = 'w in weeks'
                :key = 'w.weekNum'
                :id = prepareRef(w.weekNum)
                :week = 'w'
                :weekNum = 'w.weekNum'
                :class= "w.status"
            ></week-list-item>
        </ul>
    </div>
</template>

<script>
import WeekListItem from './WeekListItem'

export default {
    data(){
        return{

        }
    },
    props: {
        weeks: {
            type: Array
        } ,
        currentWeek:{ 
            type: Number
        }
    },
    methods:{
        focusThisWeek(){
            if(this.currentWeek>4){
                document.querySelector(`#week${this.currentWeek-4}`).scrollIntoView({behavior:"smooth"});
            }
        },
        prepareRef(num){
            return `week${num}`
        }
    },
    mounted(){
        setTimeout(this.focusThisWeek, 2000)
    },
    components:{
        WeekListItem
    }
}
</script>

<style>
    .week-list{
        height: 279px;
        overflow: scroll;
        font-size: 12px;
    }
    ul{
        margin: 0;
        padding: 0;
    }
</style>