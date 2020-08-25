<template>
  <li>
    {{week.weekText}}
  </li>
</template>

<script>
export default {
    props:{
        week : Object
    }
}
</script>

<style scoped>
    li{
        position: relative;
        text-align: left;
        padding : 5px 0 5px 10px;
        border-bottom: 1px solid gray;  
        font-weight: 700;
    }
    li::before{
        display: inline-block;
        content: attr(weekNum);
        height: 24px;
        width: 24px;
        border-radius: 50%;
        color: white;
        font-weight: 700;
        text-align: center;
        background-color: green;
        line-height: 24px;
        margin-right: 10px;
    }
    li.passed::before{
        background-color: black;
    }
    li.future::before{
        background-color: lightgray;
    }
    li.future{
        color: lightgray;
    }

</style>