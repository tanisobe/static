<template>
<div class="row">
    <div v-for="player in players" :key=player.name class="col-sm-4">
       <div class="card bg-light mb-3">
           <div class="card-header">
               <h4 class="card-title">{{ player.name }} HP {{player.hp}} </h4>
            </div>
           <div class="card-body">
               <history :history="player.mush"></history>
           </div>
       </div>
   </div>
</div>
</template>

<script>
import history from "./History.vue"
export default{
    data () {
        return { 
            players: []
        }
    },
    mounted: function () {
        var self = this;
        setInterval( function() {
        $.ajax({
            type: "GET",
            url: "/api/v1/players",
            success: function(response){
                self.players = JSON.parse(response);
                console.log(self.players);
        }})
        }, 500);
    },
    components:{history}
}
</script>