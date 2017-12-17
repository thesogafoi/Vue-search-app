<template>
  <div >
  <ul class="appoinment-list" >
       <add-appointment @dataRecorded='dataApt'></add-appointment>
      <appointment-item v-for="( apment , i)  in appointments" :key='i' :item="apment"></appointment-item>
  </ul>
</div>
</template>
<script>
import appointmentItem from './appointmentitem.vue'
import AddAppointment from './AddAppointment.vue'
import moment from 'moment'
export default {
    name:'appointmentsList',
  data(){
      return{

      }
  },props: ['appointments'] , 
  components:{
      'appointment-item':appointmentItem,
      'add-appointment': AddAppointment
  }, methods: {
    dataApt (value){
      this.$emit('valueReseved' , value)
    }
  }
        
}
</script>

<style scoped>
.appoinment-list{
  margin: 0;
  padding: 0;
  list-style-type: none;
  margin: 10px 5%;
  font-size: 1rem;
}
</style>
