<template>
  <div class="landing">
    <!-- HEADER -->
    <div class="header">
      <div id="pageHeader" class="header-image"></div>
      <div class="w-100 h-100 fade-layer">
        <div class="heading-text">
          <h1 class="header-title mb-2">Asamblea Cristiana Avenida Alemania</h1>
          <a class="primary-btn" @click="scrollSmoothTo('contactUs')">Contáctanos</a>
        </div>
      </div>
    </div>
    <div id="navbar" class="navbar-container">
      <ul class="horizontal-navbar my-0">
        <li class="navbar-link mx-1" @click="scrollSmoothTo('mainMessage')">
          <span class="nav-link">Qué creemos</span>
        </li>
        <li class="navbar-link mx-1" @click="scrollSmoothTo('warranties')">
          <span class="nav-link">Garantías</span>
        </li>
        <li class="navbar-link mx-1" @click="scrollSmoothTo('contactUs')">
          <span class="nav-link">Contacto</span>
        </li>
      </ul>
    </div>
    <!-- MAING MESSAGE -->
    <div id="mainMessage" class="message px-2 text-justify sticky-margin">
      <h1 class="heading-title text-center mb-2">En qué creemos</h1>
      <p class="main-message-text">
        Creemos que la Biblia es la palabra viva e inmutable de Dios. Cada palabra, aunque escritas por hombres, fueron inspiradas por Dios. Ella —la Palabra de Dios— es completamente relevante, confiable y suficiente para satisfacer todas nuestras necesidades espirituales.
        Creemos que el Señor Jesucristo es el eterno Hijo de Dios y es co-igual con Dios. Él, el unigéntio Hijo del Padre, se hizo hombre con el propósito de morir en la cruz como sustituto por nosotros, los pecadores. Fue levantado desde la muerte tres días después. Hoy Él está en el Cielo, a la diestra del Padre. Creemos en Su promesa de que volverá para llevar al Cielo a todos los creyentes, ya sea que vivan o que ya hallan partido de este mundo. Creemos que Su venida es inminente.
      </p>
    </div>
    <!-- WARRANTIES -->
    <div id="warranties" class="message px-2 text-justify sticky-margin">
      <h1 class="heading-title text-center mb-2">Garantías del Señor</h1>
      <div class="warranties-container">
        <div class="item mb-1">
          <div class="w-100 text-center">
            <img src="../assets/images/free.svg" class="w-40 text-center" alt />
          </div>
          <h3 class="text-center pa-1">La salvación es gratuita</h3>
          <p
            class="text-justify"
          >La palabra del Señor establece que la salvación es por gracia (Efesios 2:8) Gratuitamente Dios nos ofrece la salvación. No es entonces algo bueno en nosotros u obras nuestras las que nos permitiran lograr la salvación.</p>
        </div>
        <div class="item mb-1">
          <div class="w-100 text-center">
            <img src="../assets/images/endless.svg" class="w-40 text-center" alt />
          </div>
          <h3 class="text-center pa-1">La salvación no se pierde</h3>
          <p
            class="text-justify"
          >Un creyente, verdaderamente convertido, ha sido redimido y libertado (comprado por precio), justificado, santificado, reconcilidado con Dios. Ha nacido de nuevo.</p>
        </div>
        <div class="item mb-1">
          <div class="w-100 text-center">
            <img src="../assets/images/gift.svg" class="w-40" alt />
          </div>
          <h3 class="text-center pa-1">La salvación es para ti</h3>
          <p
            class="text-justify"
          >La Biblia dice (Juan 3:36): El que cree en el Hijo tiene vida eterna; pero el que rehúsa creer en el Hijo no verá la vida, sino que la ira de Dios está sobre él.</p>
        </div>
      </div>
    </div>
    <!-- CONTACT -->
    <div id="contactUs" class="message px-2 text-justify sticky-margin mb-100">
      <h1 class="heading-title text-center mb-2">Contacto</h1>
      <contactForm></contactForm>
    </div>
    <div id="footer" class="py-2">
      <span class="footer-text m-0-auto">Asamblea Cristiana Avenida Alemania 2020</span>
    </div>
  </div>
</template>

<script>
import ContactForm from "@/components/contactForm.vue";
export default {
  name: "Landing",
  components: {
    contactForm: ContactForm
  },
  data() {
    return {
      scrollPosition: null
    };
  },
  methods: {
    scrollSmoothTo(elementId) {
      var element = document.getElementById(elementId);
      element.scrollIntoView({ block: "start", behavior: "smooth" });
    },
    checkArea() {}
  },
  mounted() {}
};
</script>



<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
html {
  scroll-behavior: smooth;
}

.landing {
  font-family: "Open Sans";
}

.header {
  height: 50vh;
  width: 100%;
  background: var(--ox-blue);
  position: relative;
}

.header-image {
  height: 100%;
  position: relative;
  background: url("../assets/images/church-1.jpg") no-repeat;
  background-size: cover;
  background-position: center;
}

.fade-layer {
  background: var(--platinum);
  background: linear-gradient(
    0deg,
    var(--platinum) 0%,
    var(--platinum) 0%,
    rgba(32, 31, 31, 0.315) 35%
  );
  position: absolute;
  top: 0;
}

.heading-text {
  width: 90%;
  margin: 0;
  position: absolute;
  top: 50%;
  left: 50%;
  -ms-transform: translateY(-50%);
  transform: translate(-50%, -50%);
}

.header-title {
  color: white;
  font-size: 1.7em !important;
  /* text-shadow: 0px 2px 2px rgb(2 2 2 / 92%); */
  text-shadow: 2px 2px 2px rgb(0, 0, 0);
}

.heading-title {
  font-family: "PT Serif";
  border-bottom: 4px solid var(--ox-blue);
  margin: 0 auto;
}

.navbar-container {
  position: sticky;
  position: -webkit-sticky;
  top: 0;
}

.horizontal-navbar {
  padding: 20px;
  background: var(--ox-blue);
  color: white;
}

.navbar-link {
  display: inline;
  font-size: 14px;
  padding-top: 10px;
  padding-bottom: 10px;
  cursor: pointer;
  -webkit-tap-highlight-color: transparent;
}

.sticky-margin {
  padding-top: 75px;
}

.warranties-container {
  display: flex;
  flex-flow: wrap;
  margin: 0 -5px;
}

.item {
  min-width: 250px;
  width: 250px;
  padding: 10px;
  margin: 0 auto;
}

#footer {
  width: 100%;
  background: var(--ox-blue);
  font-size: 0.8em;
  color: var(--platinum);
}

@media only screen and (min-width: 600px) {
  .header-title {
    font-size: 4vw !important;
  }

  .heading-title {
    width: 30%;
  }

  .main-message-text {
    width: 70%;
    margin: 0 auto;
  }
}

@media (hover: hover) {
  .navbar-link:hover {
    border-bottom: 2px solid var(--or-web);
  }
}
</style>
