<template>
  <span>
      {{displayDays}}:{{displayHours}}:{{displayMinutes}}:{{displaySeconds}}
 </span>
</template>

<script>
export default {
    props:["year","month","date","hour","minute","second","millisecond"],
    data(){
        return{
        displayDays:0,
        displayHours:0,
        displayMinutes:0,
        displaySeconds:0,
        }
    },
    computed:{
        //date calculation
        _seconds:() => 1000,
        _minutes(){
              return this._seconds * 60;
        },
        _hours(){
              return this._minutes * 60;
        },
        _days(){
             return this._hours * 24;
        },
        //current date get from props
        end(){
            return new Date(this.year,this.month,this.date,this.hour,this.minute,this.second,this.millisecond)
        }
    },
    mounted(){
     this.startInterval();
    },
    methods:{
        //for clean code only
        formatNum(num){
            return num < 10 ? '0' + num : num;
        },
        //main method (dom rander depend on setInterval timing)
        startInterval(){
            const timer = setInterval(()=>{
                //current date
                const now = new Date();

                /*********** static data for implement countDown functionality
                const end = new Date(2021, 10, 26, 10, 10, 10, 10);
                const distance = this.end.getTime() - now.getTime();
                **********/
                
                //end date get from props
                const distance = this.end.getTime() - now.getTime();

                //condition for clearInterval
                if(distance < 0){
                    clearInterval(timer);
                    return;
                }

                //calculate date and get all thing
                const days = Math.floor(distance / this._days);
                const hours = Math.floor((distance % this._days) / this._hours);
                const minutes = Math.floor((distance % this._hours) / this._minutes);
                const seconds = Math.floor((distance % this._minutes) / this._seconds);
                
                
                // set value all declaraing variable
                
                // this.displayDays = days < 10 ? '0' + days : days;
                /* for clean code */
                this.displayDays = this.formatNum(days);

                // this.displayHours = hours < 10 ? '0' + hours : hours;
                /* refactor clean code */
                this.displayHours = this.formatNum(hours);

                // this.displayMinutes = minutes < 10 ? '0' + minutes : minutes;
                /* refactor clean code */
                this.displayMinutes = this.formatNum(minutes);

                // this.displaySeconds = seconds < 10 ? "0" + seconds : seconds;
                /* refactor clean code */
                this.displaySeconds = this.formatNum(seconds);
                
            }, 1000); 
        },
       
    }

}
</script>

<style>

</style>