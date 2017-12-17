<template>
<div id="main-app">
<appointment-list :appointments="theAppointment" @valueReseved='pushData' @requestRemove="removeFunction"></appointment-list>


</div>
</template>

<script>

import appointmentsList from './appointment.vue';
import _ from 'lodash';
export default {
  name: 'index',
  data () {
    return {
      theAppointment: '',
    }
  },created(){
    $.getJSON('./build/apment.json')
    .done(info=>{
      this.theAppointment = info;

    });
  } , components:{
    'appointment-list' : appointmentsList
  }, methods:{
      pushData: function(value){
        console.log( value)
        this.theAppointment.push(value);
      },
      removeFunction: function(apt){
        this.theAppointment = _.without(this.theAppointment , apt);
        console.log(this.theAppointment);
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
