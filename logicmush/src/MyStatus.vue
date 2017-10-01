<<template lang="pug">
    <div class="col-sm-8">
       <div class="card bg-light mb-3" style="max-width: 20rem;">
           <input v-model="name" class="card-header" @keyup="register">
           <div class="card-body">
               <h4 class="card-title">HP:{{ hp }}</h4>
           </div>
       </div>
    </div>
</template>

<<script>
export default {
    Vue.component('mystatus',{
      template: mystatusTemplate,
      data: function(){
          return { 
              id: Nan,
              hp: 3,
              name: ''
           }
      },
      methods: {
          register: function(event){
              data = {name: this.name}
              $.ajax({
                  type: "POST",
                  url: "/api/v1/register",
                  contentType: "application/json; charset=utf-8",
                  data: JSON.stringify(data)
              });
          }
      }
    });
}
</script>
