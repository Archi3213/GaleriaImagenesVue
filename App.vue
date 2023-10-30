<template>
  <div id="app">
    <h1>Galería de imágenes con Vue</h1>
    <div class="gallery">
      <div v-for="image in images" :key="image.id" class="item">
        <img :src="image.url" :alt="image.title">
        <p>{{ image.title }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      images: [
        { id: 1, url: "https://as01.epimg.net/diarioas/imagenes/2022/05/29/actualidad/1653826510_995351_1653826595_noticia_normal_recorte1.jpg", title: "Perro" },
        { id: 2, url: "https://s1.ppllstatics.com/lasprovincias/www/multimedia/202112/12/media/cortadas/gatos-kb2-U160232243326NVC-1248x770@Las%20Provincias.jpg", title: "Gato" },
        { id: 3, url: "https://www.arteescuela.com/wp-content/uploads/2022/10/como-dibujar-un-pajaro-paso-a-paso.jpg", title: "Pájaro" },
        { id: 4, url: "https://concepto.de/wp-content/uploads/2018/08/Londres-e1533855310803.jpg", title: "Ciudad" },
        { id: 5, url: "https://concepto.de/wp-content/uploads/2018/08/monta%C3%B1a-clima-min-e1533762913759.jpg", title: "Montaña" },
        { id: 6, url: "https://e00-marca.uecdn.es/assets/multimedia/imagenes/2022/09/20/16636691477600.jpg", title: "Coches" }
      ]
    };
  }
};
</script>

<style>
.gallery {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 10px;
}

.item {
  text-align: center;
  border: 2px solid black;
  border-radius: 3px;
  box-shadow:0 2px 5px 0 rgba(0,0,0,0.16),0 2px 10px 0 rgba(0,0,0,0.12);
}

img {
  width: 100%;
}
</style>
