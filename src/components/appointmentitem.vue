
<template> 
<li class="pet-item media">

<div class="media-left">
    <button class="pet-delete btn btn-xs btn-danger"><span class="glyphicon  glyphicon-remove"></span></button>
</div><!--Media Left-->
<div class="pet-info media-body">
<div class="pet-head">
    <span class="pet-name">{{item.petName}}</span>
    <span class="apt-date pull-right" style="margin-right:20px;">{{formattedDate}}</span>
</div>

<div class="ower-name">
    <span class="label-item">Owner: </span>
    <span>{{item.petOwner}}</span>
</div>
<div class="apt-notes">{{item.aptNotes}}</div>
</div>
</li>

</template>

<script>
import moment from 'moment'
    export default{
        name: 'appointmentItem', 
        props: ['item'], 
        computed:{
            formattedDate:function(){
                return moment(new Date(this.item.aptDate)).format('Y-MM-DD, h:mm a');
            }
        }
    }

</script>


<style scoped>

  .pet-item {
    border-bottom: 1px dotted gray;
    padding-bottom: 10px;
  }

  .pet-item:last-child {
    border-bottom: none;
  }

  .pet-name {
    font-weight: 600;
    color: #337ab7;
    font-size: 1.3em;
    line-height: 100%;
  }

  .pet-info {
    font-size: 1.7em;
  }

  .label-item {
    font-weight: 600;
    color: #667B82;
  }
  
  .pet-delete {
    font-size: 1.2em;
  }

  .apt-date {
    font-style: italic;
  }

  [contenteditable]:focus {
    outline: none;
    background: #EEE8D6; 
  }
</style>
  

