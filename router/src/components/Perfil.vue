<template>
  <div id="perfil">
    <!-- <div class="perfil-b">
      <h1>Perfil</h1>
    </div> -->

    <div class="row-perfil-1">
      <div class="box-perfil">
        <img
          src="https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/39ac6b8e-c8c9-4d20-a781-2b36215bf34a/d9zlxcu-fc307955-40c3-498b-96a9-cd0fce13e088.png?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOiIsImlzcyI6InVybjphcHA6Iiwib2JqIjpbW3sicGF0aCI6IlwvZlwvMzlhYzZiOGUtYzhjOS00ZDIwLWE3ODEtMmIzNjIxNWJmMzRhXC9kOXpseGN1LWZjMzA3OTU1LTQwYzMtNDk4Yi05NmE5LWNkMGZjZTEzZTA4OC5wbmcifV1dLCJhdWQiOlsidXJuOnNlcnZpY2U6ZmlsZS5kb3dubG9hZCJdfQ._G_saWbVESmLRNSbyUGeNbxCW-sDs_2BFfQQrJDE280"
          width="200"
        />
      </div>
      <div class="box-perfil">
        <h3>{{ negocios[$route.params.id - 1].negocio }}</h3>
        <h5>{{ negocios[$route.params.id - 1].frase }}</h5>
        <a class="link" :href="negocios[$route.params.id - 1].correo"
          ><i class="fas fa-envelope"></i>Correo</a
        >
        <a class="link" :href="negocios[$route.params.id - 1].website"
          ><i class="fas fa-globe-americas"></i>Website</a
        >
      </div>
      <div class="box-perfil">
        <span
          ><b>Dirección:</b>
          {{ negocios[$route.params.id - 1].direccion }}</span
        >
        <br />
        <span
          ><b>Teléfono:</b> {{ negocios[$route.params.id - 1].telefono }}</span
        ><br />
        <span><b>Correo:</b> {{ negocios[$route.params.id - 1].correo }}</span>
      </div>
    </div>






    <div class="row-perfil-2">
         <div class="box-perfil">

         </div>
         <div class="box-perfil">

         </div>

    </div>



  </div>
</template>



<script>
import axios from "axios";
export default {
  name: "perfil",

  data() {
    return {
      negocios: null,
      //   idRouting: `${$route.params.id}`,
    };
  },

  mounted() {
    axios
      .get("https://602442a36bf3e6001766c198.mockapi.io/api/v1/profiles")
      .then((response) => (this.negocios = response.data))
      .catch((e) => console.log(e));
  },
};
</script>









<style >
#perfil {
  background: #f9f9f9cc;

  background-image: url("https://www.dchweb.org/sites/doctors-community-hospital/files/awards_iStock-1055161930_0.jpg");
  background-blend-mode: lighten;
  height: 100vh;
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  padding-top: 100px;
}

#perfil h1 {
  color: #fff;
}

.perfil-b {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: rgba(0, 0, 0, 0.651);
  height: 200px;
}

.row-perfil-1 {
  display: -ms-flexbox;
  display: -webkit-flex;
  display: flex;
  -webkit-flex-direction: row;
  -ms-flex-direction: row;
  flex-direction: row;
  -webkit-flex-wrap: wrap;
  -ms-flex-wrap: wrap;
  flex-wrap: wrap;
  -webkit-justify-content: center;
  -ms-flex-pack: center;
  justify-content: center;
  -webkit-align-content: stretch;
  -ms-flex-line-pack: stretch;
  align-content: stretch;
  -webkit-align-items: flex-start;
  -ms-flex-align: start;
  align-items: center;

  background-color: #fff;
  width: 80%;
  margin: 0 auto;
  border-radius: 60px;
  padding: 20px;
  
}

.box-perfil h3{
    margin: 0;
    line-height: 25px;
}
.box-perfil h5{
    margin: 0;
    line-height: 35px;
}

.row-perfil-1 .box-perfil:nth-child(1) {
  width: 300px;
  -webkit-order: 0;
  -ms-flex-order: 0;
  order: 0;
  -webkit-flex: 1 1 auto;
  -ms-flex: 1 1 auto;
  flex: 0 1 auto;
  -webkit-align-self: auto;
  -ms-flex-item-align: auto;
  align-self: center;
}

.row-perfil-1 .box-perfil:nth-child(2) {
    width: 500px;
  -webkit-order: 0;
  -ms-flex-order: 0;
  order: 0;
  -webkit-flex: 2 1 auto;
  -ms-flex: 2 1 auto;
  flex: 2 1 auto;
  -webkit-align-self: auto;
  -ms-flex-item-align: auto;
  align-self: auto;
  text-align: left;
}

.row-perfil-1 .box-perfil:nth-child(3) {
   
  border: none;
  border-left: 1px solid #00000025;
  height: auto;
  padding-left: 20px;
  -webkit-order: 0;
  -ms-flex-order: 0;
  order: 0;
  -webkit-flex: 2 1 auto;
  -ms-flex: 2 1 auto;
  flex: 2 1 auto;
  -webkit-align-self: auto;
  -ms-flex-item-align: auto;
  align-self: auto;
  text-align: left;
}

.link {
  background-color: #003c93;
  color: #000;
  font-size: 14px;
  font-weight: 700;
  border-radius: 40px;
  color: #fff;
  padding: 5px;
  padding-left: 10px;
  padding-right: 10px;
  text-decoration: none !important;
  margin-right: 5px;
  line-height: 0px;
}

.link:hover {
  background-color: #000;
}

.link i {
  padding-top: 5px;
  padding-right: 5px;
}









.row-perfil-2 {
    display: -ms-flexbox;
    display: -webkit-flex;
    display: flex;
    -webkit-flex-direction: row;
    -ms-flex-direction: row;
    flex-direction: row;
    -webkit-flex-wrap: wrap;
    -ms-flex-wrap: wrap;
    flex-wrap: wrap;
    -webkit-justify-content: center;
    -ms-flex-pack: center;
    justify-content: center;
    -webkit-align-content: stretch;
    -ms-flex-line-pack: stretch;
    align-content: stretch;
    -webkit-align-items: flex-start;
    -ms-flex-align: start;
    align-items: flex-start;
    width: 82%;
    margin: 0 auto;
    margin-top: 30px;
    
    }

.row-perfil-2 .box-perfil:nth-child(1) {
    -webkit-order: 0;
    -ms-flex-order: 0;
    order: 0;
    -webkit-flex: 2 1 auto;
    -ms-flex: 2 1 auto;
    flex: 2 1 auto;
    -webkit-align-self: auto;
    -ms-flex-item-align: auto;
    align-self: auto;
   
    background-color: #000;
  
  margin: 0 auto;
   margin-right: 20px;
  border-radius: 60px;
  padding: 20px;
    }

.row-perfil-2 .box-perfil:nth-child(2) {
    -webkit-order: 0;
    -ms-flex-order: 0;
    order: 0;
    -webkit-flex: 3 1 auto;
    -ms-flex: 3 1 auto;
    flex: 3 1 auto;
    -webkit-align-self: auto;
    -ms-flex-item-align: auto;
    align-self: auto;
    
    background-color: #000;
  
  margin: 0 auto;
  margin-left: 20px;
  border-radius: 60px;
  padding: 20px;
    }

</style>