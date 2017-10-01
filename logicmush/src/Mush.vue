<<template>
    <div>
        <img v-b-popover.hover.html='message' title="Effect" v-bind:src='"https://tanisobe.github.io/static/m" + mush.mtype + "_" + mush.color + ".jpg"' class="rounded float-left" >
        <b-button @click="eat(mush)">eat</b-button>
    </div>
</template>

<<script>
export default {
  props: ['mush'],
  computed: {
      message: function () {
          var msg = ''
          for ( var day in this.mush.effects){
              msg += 'Day' + day + ':' + this.mush.effects[day].msg + '<br>';
          }
          return msg
      },
  },
  methods: {
    eat: function (mush) {
        $.ajax({
            type: "GET",
            url: "/api/v1/eat/" + mush.id,
        });
    }
  },
}
</script>