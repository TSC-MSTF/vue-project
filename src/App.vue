<template>
  <div class="container">
    <h3 class="text-center mt-3">Kelime Değiştirme</h3>
    <div class="d-flex justify-content-center align-content-center flex-row">
      <div class="card p-4 mt-3 shadow">
        <form style="width: 350px">
          <div class="form-group">
            <label>Lütfen Kelime giriniz !!</label>
            <input v-model="kelime " type="text" class="form-control" placeholder="Kelime Giriniz" />
            <hr />
            <button
              @click="change() ; selected = false "
              type="button"
              class="btn btn-warning"
            >Değiştir</button>

            <button @click="change" type="button" class="btn btn-warning">Geri Al</button>
          </div>
          <!--
          <p>
            <b>Değiştirilmiş Kelime yöntem I :</b>
            {{kelime}}
          </p>

          -->

          <p>
            <b>Kelimenin Değiştirilmiş Hali :</b>
            {{topla}}
          </p>

          <p>Geri Al : {{geriAl}}</p>
        </form>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      kelime: null,
      topla: "",
      geriAl: "",
      selected: true,
    };
  },

  methods: {
    change: function () {
      for (var i = 0; i < this.kelime.length; i++) {
        if (this.selected == true) {
          if (this.kelime[i] == "a") {
            this.topla = this.topla + "e";
          } else {
            this.topla = this.topla + this.kelime[i];
          }
        }

        if (this.selected == false) {
          this.geriAl = this.geriAl + this.kelime[i];
        }
      }
      // Kısa çözüm
      /*
      for (var i = 0; i < this.kelime.length; i++) {
        this.kelime = this.kelime.replace("a", "e");
      }
      */
      // Uzun çözüm
    },
  },

  /*
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
   */
};
</script>
