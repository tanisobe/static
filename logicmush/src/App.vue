<template>
  <div id="app" class="container">
    <status></status>
    <mushlist></mushlist>
    <register v-if="showRegister" @close="showRegister = false"></register>
    <reset></reset>
  </div>
</template>

<script>
import status from './Status.vue'
import register from './Register.vue'
import mushlist from './MushList.vue'
import Vue from 'vue'
import BootstrapVue from 'bootstrap-vue'
import reset from './Reset.vue'
import 'bootstrap'
import 'bootstrap-vue'
Vue.use(BootstrapVue);
export default {
  name: 'app',
  data () {
    return {
      "showRegister": true
    }
  },
  components:{status, register, mushlist,reset}
}
</script>