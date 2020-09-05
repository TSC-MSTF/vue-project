<template>
  <div class="container">
    <h3 class="text-center mt-3">Yasaklı Kelime</h3>
    <div class="d-flex justify-content-center align-content-center flex-row">
      <div class="card p-4 mt-3  shadow">
        <form style="width: 350px" >
          <div class="form-group">
            <label>Lütfen Kelime giriniz !!</label>
            <input v-model="kelime " type="text" class="form-control" placeholder="Kelime Giriniz" >
            
          </div>
         <p>Kelime : {{kelime}}</p>
        </form>
      </div>
    </div>
  </div>
</template>
<script>
  export default {
    data() {
      return {
       
        kelime : null,

       
      }
    },
    
    watch : {

      kelime : function(){
        this.kelime = this.kelime.toLowerCase();
        var yasakla = ["araba","otomobil", "araç","taşıt"]
        for (var i = 0 ; i < yasakla.length; i++){
          if (this.kelime.includes(yasakla[i])){
            this.kelime = this.kelime.replace(yasakla[i], "*".repeat(yasakla[i].length))
            //alert("Argo içerikli mesaj giremezsiniz !!!")
          }
        }

      }



    },
   
  }
</script>
