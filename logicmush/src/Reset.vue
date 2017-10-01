<template>
<b-button @click="reset">reset</b-button>
</template>

<script>
export default {
  methods:{
      reset: function (event) {
        $.ajax({
            type: "GET",
            url: "/api/v1/reset"
        })
        .then(
            function(){
                location.reload();
            }
        );
      }
  }
}
</script>