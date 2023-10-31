<template>
    <div class="gallery">
      <div class="artwork-row">
        <div class="artwork" @mouseover="showInfo(1)" @mouseout="hideInfo(1)">
          <img src="https://i.pinimg.com/564x/34/bb/6d/34bb6dd4b92445cd93ccd576132cbbd2.jpg" alt="Paris 1" @error="handleImageError(1)" />
          <div v-if="showInfo1" class="info" @click="showDetails(1)">
            <p>Paris 1 - Descripción de la pintura. Haz clic para obtener más detalles.</p>
          </div>
        </div>
        <div class="artwork" @mouseover="showInfo(2)" @mouseout="hideInfo(2)">
          <img src="https://static.arteinformado.com/resources/app/docs/evento/27/161827/tour_eiffel_cafe.jpg" alt="Paris 2" @error="handleImageError(2)" />
          <div v-if="showInfo2" class="info" @click="showDetails(2)">
            <p>Paris 2 - Descripción de la pintura. Haz clic para obtener más detalles.</p>
          </div>
        </div>
        <div class="artwork" @mouseover="showInfo(3)" @mouseout="hideInfo(3)">
          <img src="https://imagenes.elpais.com/resizer/cFakMxU3PYO9HG2KjSR5vXFbzgI=/1200x0/arc-anglerfish-eu-central-1-prod-prisa.s3.amazonaws.com/public/X4C6RCK2QUHB3A3X2TSNTCKXRA.jpg" alt="Paris 3" @error="handleImageError(3)" />
          <div v-if="showInfo3" class="info" @click="showDetails(3)">
            <p>Paris 3 - Descripción de la pintura. Haz clic para obtener más detalles.</p>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Gallery',
    data() {
      return {
        showInfo1: false,
        showInfo2: false,
        showInfo3: false,
      };
    },
    methods: {
      showInfo(index) {
        this[`showInfo${index}`] = true;
      },
      hideInfo(index) {
        this[`showInfo${index}`] = false;
      },
      handleImageError(index) {
        this[`showInfo${index}`] = true;
      },
    },
  };
  </script>
  
  <style scoped>
  .gallery {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-image: url('./GaleriaImagenesVue/photos/GaleriaFondo.jpg'); /* Añade la ruta de tu imagen de fondo */
    background-size: cover;
    padding: 20px;
    color: white;
  }
  
  .artwork-row {
    display: flex;
    justify-content: space-between;
  }
  
  .artwork {
    flex: 1;
    margin: 10px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
    transition: transform 0.3s ease;
    position: relative;
    cursor: pointer;
  }
  
  .artwork img {
    width: 100%;
    height: auto;
  }
  
  .info {
    position: absolute;
    background: rgba(0, 0, 0, 0.7);
    color: white;
    padding: 10px;
    border-radius: 5px;
    bottom: 0;
    left: 0;
    right: 0;
    transform: translateY(100%);
    transition: transform 0.3s ease;
    opacity: 0;
    cursor: pointer;
  }
  
  .artwork:hover {
    transform: scale(1.1);
  }
  
  .artwork:hover .info {
    transform: translateY(0);
    opacity: 1;
  }
  </style>
  
  