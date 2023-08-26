<template>
    <div class="results">
        <p>Reaction Time: {{ ScoreR }}ms</p>
        <p class="Rank">Rank: {{ rank }}</p>
    </div>
</template>

<script>
    export default{
        props:['ScoreR'],
        data(){
            return{
                rank:null
            }
        },
        mounted(){
            if(this.ScoreR<200){
                this.rank = "God Like Speed"
            }
            else if(this.ScoreR<300){
                this.rank = "Rapid Reflexes"
            }
            else if(this.ScoreR<400){
                this.rank = "Average Human"
            }
            else if(this.ScoreR<500){
                this.rank = "Noob"
            }
            else{
                this.rank = "Not even a Human"
            }
        }
    }
</script>

<style>

</style>