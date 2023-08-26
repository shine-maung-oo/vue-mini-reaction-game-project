<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
    click here <span>{{ delay }}</span>
  </div>
</template>

<script>
export default {
    name: 'app',
    props: [ 'delay'],
    data(){
        return{
            showBlock: false,
            score: 0,
            timer: null,
        }
    },
    mounted(){
        setTimeout(()=>{
            this.showBlock=true;
            this.startTimer();
        },this.delay);
    },
    // updated() {
    //     console.log("updated data");
    // },
    methods:{
        startTimer(){
            this.timer=setInterval(() => {
                this.score+=50;
            }, 50);
        },
        stopTimer(){
            // this.showBlock=false;
            clearInterval(this.timer);
            // console.log(this.score);
            this.$emit('endGame',this.score);
        },
    }
}
</script>

<style>
    .block {
        background-color: aquamarine;
        width: 400px;
        height: 200px;
        margin: 50px auto;
        padding: 40px;
    }
</style>