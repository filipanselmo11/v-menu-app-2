<template>
  <div>
    <div class="vertical-menu">
      <a>Editar Desenho</a>
      <a>Atribuir Evento</a>
      <a>Atribuir Categoria</a>
    </div>
  </div>
</template>

<script>
export default {
  name: "HtmlMenu",
};
</script>

<style scoped>
.vertical-menu {
  width: 149px !important;
  height: 102px !important;
  margin-left: 461px !important;
  border-radius: 4px !important;
}

.vertical-menu a {
  background-color: #2F4966 !important;
  color: orangered !important;
  display: block !important;
  padding: 12px !important;
  text-decoration: none !important;

}

.vertical-menu a:hover {
  background-color: rgb(249, 18, 249);
}

.vertical-menu a.active {
  background-color: #04AA6D;
  color: white;
}

</style>