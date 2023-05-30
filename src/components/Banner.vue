<template>
  <div class="main-banner d-flex" :style="{ backgroundColor: corDeFundo }">
    <div class="text-center banner-content">
      <img :src="logo" :alt="alt" id="logo" />
      <h1 class="fs-1 text-light">Lucas Cavalcante</h1>
      <p class="fs-3">
        Desenvolvedor web fascinado por criar soluções digitais incríveis
      </p>
      <button
        type="button"
        class="btn btn-warning btn-lg rounded-pill btn-custom"
        @click="redirectToContact"
      >
        Entrar em contato
      </button>
    </div>
  </div>
</template>

<script>
import { onMounted } from "vue";
import ScrollReveal from "scrollreveal";

export default {
  name: "Banner",
  data() {
    return {
      logo: "/img/logo.png",
      alt: "Logo marca",
      corDeFundo: "#212529",
    };
  },
  methods: {
    redirectToContact() {
      this.$router.push("/contact");
    },
  },
  setup() {
    onMounted(() => {
      const sr = ScrollReveal({
        distance: "30px",
        origin: "left",
        duration: 1000,
        delay: 200,
        easing: "ease",
      });

      sr.reveal(".banner-content");
    });
  },
};
</script>

<style scoped>
h1 {
  font-family: "Patua One", cursive;
  font-weight: 700;
}

p {
  color: #c4c4c4;
}

.btn-custom {
  padding: 16px 50px;
  font-size: 24px;
  font-weight: 700;
}

.main-banner {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  min-height: 100vh;
  padding-top: 60px;
}

.banner-content {
  margin: auto;
  visibility: hidden;
}

#logo {
  width: 180px;
  margin-bottom: 10px;
  user-select: none;
}

@media (max-width: 368px) {
  #logo {
    width: 100px;
  }
  .main-banner h1 {
    font-size: 24px;
  }

  .main-banner p {
    font-size: 18px;
  }

  .main-banner .btn-custom {
    font-size: 20px;
  }
}
</style>
