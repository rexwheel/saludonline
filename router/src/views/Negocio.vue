<template>
  <div id="inicio">
    <div class="busqueda">
      <h1>Negocios</h1>
    </div>

    <div class="flex-container" v-for="negocio in negocios" :key="negocio.id">
      <div class="flex-item">
        <!-- <img :src="negocio.perfil" width="100px"> -->
        <img
          src="https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/39ac6b8e-c8c9-4d20-a781-2b36215bf34a/d9zlxcu-fc307955-40c3-498b-96a9-cd0fce13e088.png?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOiIsImlzcyI6InVybjphcHA6Iiwib2JqIjpbW3sicGF0aCI6IlwvZlwvMzlhYzZiOGUtYzhjOS00ZDIwLWE3ODEtMmIzNjIxNWJmMzRhXC9kOXpseGN1LWZjMzA3OTU1LTQwYzMtNDk4Yi05NmE5LWNkMGZjZTEzZTA4OC5wbmcifV1dLCJhdWQiOlsidXJuOnNlcnZpY2U6ZmlsZS5kb3dubG9hZCJdfQ._G_saWbVESmLRNSbyUGeNbxCW-sDs_2BFfQQrJDE280"
          width="80"
        />
      </div>
      <div class="flex-item">
        <h3>{{ negocio.negocio }}</h3>
        <span>{{ negocio.frase }}</span>
        <br />
        <a :href="negocio.correo"><i class="fas fa-envelope"></i>Correo</a>
        <a :href="negocio.website"
          ><i class="fas fa-globe-americas"></i>Websites</a
        >
        <br />
        <span> <b>Dirección:</b> {{ negocio.direccion }} </span>
      </div>
    </div>
  </div>
</template>


<script>
import axios from "axios";
export default {
  name: "Inicio",

  data() {
    return {
      negocios: null,
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

<style>
#inicio {
  display: flex;
  height: auto;
  width: 100%;
  flex-direction: column;

  align-items: center;
}

.busqueda {
  display: flex;
  height: auto;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 200px;
  width: 100%;

  color: #fff;
  margin-bottom: 50px;
  background: url(https://www.prospectfactory.com.mx/wp-content/uploads/2016/01/doctor-1280x720.jpg);

  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  background-color: rgba(0, 0, 0, 0.644);
  background-blend-mode: multiply;
}

h3 {
  color: #003c93;
  line-height: 0px;
  font-size: 30px;
  margin-bottom: 10px;
}

h5 {
  font-size: 18px;
  line-height: 0px;
  color: #757575;
}
span {
  line-height: 40px !important;
}

#inicio a {
  background-color: #003c93;
  font-size: 14px;
  font-weight: 700;
  border-radius: 40px;
  color: #fff;
  padding: 5px;
  padding-left: 10px;
  padding-right: 10px;
  text-decoration: none;
  margin-right: 5px;
  line-height: 0px;
}

#inicio a:hover {
  background-color: #000;
}

#inicio a i {
  padding-top: 5px;
  padding-right: 5px;
}

.flex-container {
  width: 800px;
  height: auto;

  margin: 20px;
  border-radius: 20px;

  background-color: #fff;

  box-shadow: 0px 16px 40px rgba(102, 133, 163, 0.1);
  border-radius: 25px;
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
}

.flex-item:nth-child(1) {
  width: 200px;
  -webkit-order: 0;
  -ms-flex-order: 0;
  order: 0;
  -webkit-flex: 1 1 auto;
  -ms-flex: 1 1 auto;
  flex: 1 1 auto;
  -webkit-align-self: auto;
  -ms-flex-item-align: auto;
  align-self: auto;
}

.flex-item:nth-child(2) {
  width: 400px;
  height: auto;
  -webkit-order: 0;
  -ms-flex-order: 0;
  order: 0;
  -webkit-flex: 3 1 auto;
  -ms-flex: 3 1 auto;
  flex: 3 1 auto;
  -webkit-align-self: auto;
  -ms-flex-item-align: auto;
  align-self: auto;
  text-align: left;
  padding: 10px 20px 10px 20px;
}
.flex-item:nth-child(2):hover {
  background-color: #003c93;
  border-radius: 0px 40px 40px 0px;
}

.flex-item:nth-child(2):hover a {
  background-color: #fff !important;
  color: #003c93 !important;
}

.flex-item:nth-child(2):hover h3 {
  color: #fff !important;
}

.flex-item:nth-child(2):hover span {
  color: #fff !important;
}
</style>