<template>
<div class="row">
    <div v-for="(mush, day) in history" :key="day" class="col-sm-4">
        <p>Day{{day}}</p>
        <mush :mush="mush"></mush>
   </div>
</div>
</template>

<script>
import mush from './Mush.vue'

export default {
  props: ['history'],
  components:{mush}
}
</script>
