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
            
        </div>
         <br> <br>
        <div class="day">{{ day }}</div>
    </div>
    
</template>

<script>
export default {
    name: 'realTimeClock',
    data() {
        return {
            hours: 0,
            minutes: 0,
            seconds: 0          
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

<style>
#app {
  font-family: System-ui;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;

}
h1{
    color: white;
    margin-bottom: 100px;
    font-size: 90px;
  
}
h1:hover{
    color: white;
    animation: cf 1s ease-in-out infinite;
}
@keyframes cf{
    0%{color: tomato;}
    20%{color: rgb(255, 230, 0);}
    40%{color: rgb(71, 255, 80);}
    60%{color: rgb(71, 255, 230);}
    80%{color: rgb(71, 187, 255);}
    100%{color: rgb(212, 71, 255);}
}
body{
    background: #3d4042;
     align-content: center;
      margin-left: 10%;
      margin-right: 10%;
}

.LCD{
    /* display: flex; */
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    font-size: 90px;
    background: rgb(44, 44, 44);
    color: rgb(255, 255, 255);
    border-radius: 30px;
}
.divider{
    color: rgb(122, 122, 122);
    animation: cf 1s ease-in-out infinite;
}

.hours{
    background: rgba(99, 99, 99, 0.486);
    padding: 10px;
    border-radius: 20px;
    margin-right: 10px;
    margin-left: 10px;
}
.hours:hover{
    animation: cf 1s ease-in-out infinite;
}
.minutes{
     background: rgba(99, 99, 99, 0.486);
    padding: 10px;
    border-radius: 20px;
    margin-right: 10px;
      margin-left: 10px;
}
.minutes:hover{
    animation: cf 1s ease-in-out infinite;
}
.seconds{
    background: rgba(99, 99, 99, 0.486);
    padding: 10px;
    border-radius: 20px;
    margin-right: 10px;
    margin-left: 10px;
}
.seconds:hover{
    animation: cf 1s ease-in-out infinite;
}

@media screen and (max-width: 600px) { 
    h1{
        margin-bottom: 100px;
        font-size: 60px;
    }
    .LCD{

    justify-content: center;
    align-items: center;
    text-align: center;
    font-size: 50px;
    background: rgb(44, 44, 44);
    color: rgb(255, 255, 255);
    border-radius: 30px;
}
}
</style>>

