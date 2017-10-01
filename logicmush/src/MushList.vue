<template>
<div class="row">
    <div v-for="mush in mushes" :key=mush.type class="col-sm-2">
        <p>{{mush.mtype}}</p>
        <mush :mush="mush"></mush>
   </div>
</div>
</template>

<script>
import mush from './Mush.vue'
export default{
    data () {
        return { 
            mushes: []
        }
    },
    mounted: function () {
        var self = this;
        setInterval( function() {
        $.ajax({
            type: "GET",
            url: "/api/v1/mushes",
            success: function(response){
                self.mushes = JSON.parse(response);
        }})
        }, 1000);
    },
    components:{mush}
}
</script>