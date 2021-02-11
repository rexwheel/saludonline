<template>
  <div class="perfil">
    <div class="busqueda">
      <h1>Perfil</h1>
    </div>

    <div>
      <h1>Perfil del cliente desde componente: {{ $route.params.id }}</h1>
      
    </div>
  </div>
</template>

<script>
export default {
  name: "Cliente",
};
</script>

<style >
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
</style>