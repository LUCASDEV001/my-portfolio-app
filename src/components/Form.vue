<template>
  <div class="content" :style="{ backgroundColor: corDeFundo }">
    <!-- Form -->
    <div class="banner-content form-wrapper">
      <form
        id="contactForm"
        action="https://formsubmit.co/cavalcantelucas20@hotmail.com"
        method="POST"
        data-form
      >
        <h3 class="text-center text-light">Entre em Contato</h3>
        <!-- Name -->
        <div class="mb-3 text-light">
          <label class="form-label" for="name">Nome</label>
          <input
            class="form-control"
            id="name"
            type="text"
            name="name"
            placeholder="Digite seu nome"
            required
          />
        </div>

        <!-- Email -->
        <div class="mb-3 text-light">
          <label class="form-label" for="emailAddress">E-mail</label>
          <input
            class="form-control"
            id="emailAddress"
            type="email"
            name="email"
            placeholder="Digite seu E-mail"
            required
          />
        </div>

        <!-- Message -->
        <div class="mb-3 text-light">
          <label class="form-label" for="message">Mensagem</label>
          <textarea
            class="form-control"
            id="message"
            name="message"
            type="text"
            placeholder="Digite sua mensagem aqui"
            style="height: 7rem"
            required
          ></textarea>
        </div>

        <!-- Form submit -->
        <div class="d-grid">
          <button class="btn btn-warning btn-lg" type="submit" data-button>
            Enviar
          </button>
        </div>

        <input type="hidden" name="_subject" value="Novo Contato!" />
        <input type="text" name="_honey" style="display: none" />
        <input type="hidden" name="_captcha" value="false" />
        <input
          type="hidden"
          name="_next"
          value="http://localhost:8080/contact"
        />
      </form>
    </div>
  </div>
</template>

<script>
import { onMounted } from "vue";
import ScrollReveal from "scrollreveal";

export default {
  name: "Form",
  data() {
    return {
      corDeFundo: "#212529",
    };
  },
  setup() {
    onMounted(() => {
      const sr = ScrollReveal({
        distance: "30px",
        origin: "right",
        duration: 1000,
        delay: 200,
        easing: "ease",
      });

      sr.reveal(".banner-content");

      const form = document.querySelector("[data-form]");
      const formButton = document.querySelector("[data-button]");

      formButton.addEventListener("click", () => {
        form.submit();
      });

      form.addEventListener("submit", () => {
        alert("Mensagem enviada com sucesso!");
        window.location.reload();
      });
    });
  },
};
</script>

<style scoped>
h3,
button {
  font-weight: bold;
}

.content {
  padding-top: 150px;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  min-height: 100vh;
}

.banner-content {
  margin: auto;
  visibility: hidden;
}

.form-wrapper {
  border: 1px solid #ced4da;
  padding: 20px;
  border-radius: 5px;
  max-width: 500px;
}

.form-control:focus {
  border-color: #ffca2c;
  box-shadow: none;
}

textarea {
  resize: none;
}

.success,
.error {
  text-align: center;
}

.success {
  color: greenyellow;
}

.error {
  color: tomato;
}

@media (max-width: 368px) {
  .content {
    padding-top: 100px;
  }

  .form-wrapper {
    max-width: 90%;
    margin-left: auto;
    margin-right: auto;
  }

  textarea {
    height: 3rem;
  }
}
</style>
