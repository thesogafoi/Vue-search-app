<template>
<div id="main-app">
<appointment-list :appointments="theAppointment"></appointment-list>
</div>
</template>

<script>
import appointmentsList from './appointment.vue';
export default {
  name: 'index',
  data () {
    return {
      theAppointment: '',
    }
  },created(){
    $.getJSON('https://gist.githubusercontent.com/planetoftheweb/46426d47f21f2c9245bbe23f0fb834b5/raw/afae0adf97472893288ac5cde69e7bbb770793ed/appointments.json')
    .done(info=>{
      this.theAppointment = info;
    });
  } , components:{
    'appointment-list' : appointmentsList
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
