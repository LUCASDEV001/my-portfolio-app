<template>
  <section class="services py-5 bg-light">
    <div class="container content">
      <h3 class="text-center pb-5">SERVIÇOS A OFERECER</h3>
      <div class="row pb-3">
        <div class="col-lg-4 mb-3">
          <div class="card text-center py-3">
            <div class="card-body">
              <div class="circle">
                <span><i class="fas fa-desktop"></i></span>
              </div>
              <h4 class="font-weight-bold pb-2">Web Design</h4>
              <p>
                Websites modernos e atrativos, criados com foco na usabilidade e
                experiência do usuário. Garanto layouts personalizados.
              </p>
            </div>
          </div>
        </div>

        <div class="col-lg-4 mb-3">
          <div class="card text-center py-3">
            <div class="card-body">
              <div class="circle">
                <span><i class="fa-solid fa-mobile-screen-button"></i></span>
              </div>
              <h4 class="font-weight-bold pb-2">Responsivo</h4>
              <p>
                Criação de interfaces flexíveis e adaptáveis para garantir uma
                experiência perfeita em qualquer dispositivo.
              </p>
            </div>
          </div>
        </div>

        <div class="col-lg-4 mb-3">
          <div class="card text-center py-3">
            <div class="card-body">
              <div class="circle">
                <span><i class="fa-solid fa-code"></i></span>
              </div>
              <h4 class="font-weight-bold pb-2">Desenvolvimento</h4>
              <p>
                Sistemas escaláveis e eficientes, utilizando as mais recentes
                tecnologias e boas práticas de programação.
              </p>
            </div>
          </div>
        </div>

        <div class="col-lg-4 offset-lg-2 mb-3">
          <div class="card text-center py-3">
            <div class="card-body">
              <div class="circle">
                <span><i class="fa-brands fa-searchengin"></i></span>
              </div>
              <h4 class="font-weight-bold pb-2">Otimizado para SEO</h4>
              <p>
                Aumente a visibilidade da sua marca nos mecanismos de busca com
                um website otimizado para SEO.
              </p>
            </div>
          </div>
        </div>

        <div class="col-lg-4 mb-3">
          <div class="card text-center py-3">
            <div class="card-body">
              <div class="circle">
                <span><i class="fa-brands fa-sketch"></i></span>
              </div>
              <h4 class="font-weight-bold pb-2">Design Criativo</h4>
              <p>
                Transmita a essência da sua marca por meio de elementos visuais
                inovadores, layouts envolventes e uma identidade visual coesa.
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { onMounted } from "vue";
import ScrollReveal from "scrollreveal";

export default {
  name: "ServicesList",
  setup() {
    onMounted(() => {
      const sr = ScrollReveal({
        distance: "30px",
        origin: "left",
        duration: 1000,
        delay: 200,
        easing: "ease",
      });

      sr.reveal(".content");
    });
  },
};
</script>

<style scoped>
h4 {
  font-weight: bold;
}

.card {
  border: none;
  outline: none;
  -webkit-box-shadow: -8px 6px 89px -65px rgba(0, 0, 0, 0.75);
  -moz-box-shadow: -8px 6px 89px -65px rgba(0, 0, 0, 0.75);
  box-shadow: -8px 6px 89px -65px rgba(0, 0, 0, 0.75);
}

.content {
  padding-top: 100px;
  visibility: hidden;
}

.card p {
  color: gray;
}

.circle {
  height: 70px;
  width: 70px;
  background-color: rgb(233, 231, 231);
  color: black;
  padding: 12px;
  font-size: 30px;
  border-radius: 50%;
  display: inline-block;
  margin-bottom: 20px;
}

.card:hover .circle {
  background-color: black;
  color: white;
  transition: 0.5s;
}

.services {
  position: absolute;
  left: 0;
  width: 100%;
  min-height: 100vh;
}
</style>
