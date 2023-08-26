<template>
    <div class="block" v-if="blockelement" @click="clickstop">
        <p>click me</p>
    </div>
</template>

<script>
    export default{
        props:['delay'],
        data(){
            return{
                blockelement: false,
                start: null,
                end: 0
            }
        },
        mounted(){
            setTimeout(()=>{
                this.blockelement=true
                this.clickstart()
            },this.delay)
        },
        methods:{
            clickstart(){
                this.start = setInterval(()=>{
                    this.end += 10
                },10)
            },
            clickstop(){
                clearInterval(this.start)
                console.log(this.end)
                this.$emit('endgame',this.end)
            }
        }
    }
</script>

<style>
    .block{
        width: 400px;
        padding: 75px 0px;
        cursor: pointer;
        background-color: #1e1e1e;
        color: azure;
        text-align: center;
        margin: 35px auto;
        border-radius: 15px;
    }
</style>