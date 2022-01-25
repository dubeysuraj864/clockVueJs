<template>
    <h1>Digital Clock</h1>
    <div class="container" v>
        <div class="LCD">
            <div class="hours">{{ hours }}</div>
            <div class="divider">:</div>
            <div class="minutes">{{ minutes }}</div>
            <div class="divider">:</div>
            <div class="seconds">{{ seconds }}</div> 
            <br> <br>
            <div class="date">{{ date }}</div>
        </div>
    </div>
    
</template>

<script>
export default {
    name: 'realTimeClock',
    data() {
        return {
            hours: 0,
            minutes: 0,
            seconds: 0,
             date : Date()
        }
    },
   
    methods:{
        setTime(){
            const date = new Date();
            let hours = date.getHours();
            let minutes= date.getMinutes();
            let seconds = date.getSeconds();

            hours = hours <= 9 ? `${hours}`.padStart(2,0) : hours;
            minutes = minutes <= 9 ? `${minutes}`.padStart(2,0): minutes;
            seconds = seconds <= 9 ? `${seconds}`.padStart(2.0): seconds;
            this.hours = hours;
            this.minutes= minutes;
            this.seconds= seconds;
        },
    },
    mounted(){
        setInterval(() => this.setTime(), 1000)
    }
}
</script>

<style scoped>
body{
     align-content: center;
    
}

.LCD{
    display: flex;
    text-align: center;
}
.LCD > div {
  font-family: "alarm clock";
  font-size: x-large;
}
</style>>

