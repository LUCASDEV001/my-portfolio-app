<template>
  <section class="py-5">
    <div class="container content">
      <h3 class="text-center pb-5">PORTFÓLIO</h3>
      <ul
        class="row portfolio list-unstyled mb-0 boxed-portfolio d-flex align-items-center justify-content-center"
      >
        <li class="col-md-6 col-lg-4 project" data-groups='["skill1"]'>
          <div class="card mb-0">
            <div class="project m-0">
              <figure class="portfolio-item">
                <a
                  class="hovereffect"
                  href="https://lucasdev001.github.io/realestate-page/"
                  target="_blank"
                >
                  <img class="img-responsive" :src="project1" :alt="alt" />
                  <div class="overlay"></div>
                </a>
              </figure>
            </div>

            <div class="card-body">
              <a class="card-title title-link fs-16 fw-bold"
                >LANDING PAGE IMOBILIÁRIA</a
              >
              <p class="card-text mt-5 mb-0 fs-14">
                Este é um projeto real que consiste em uma landing page voltada
                para venda de imóvel.
              </p>
            </div>
          </div>
        </li>

        <li class="col-md-6 col-lg-4 project" data-groups='["skill1"]'>
          <div class="card mb-0">
            <div class="project m-0">
              <figure class="portfolio-item">
                <a
                  href="https://lucasdev001.github.io/ProjetoBarberAgile/#home"
                  target="_blank"
                  class="hovereffect"
                >
                  <img class="img-responsive" :src="project2" :alt="alt2" />
                  <div class="overlay"></div>
                </a>
              </figure>
            </div>

            <div class="card-body">
              <a class="card-title title-link fs-16 fw-bold">BARBEARIA</a>
              <p class="card-text mt-5 mb-0 fs-14">
                Este é apenas um dos meus projetos de amostra. Neste caso, para
                barbearia.
              </p>
            </div>
          </div>
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
import { onMounted } from "vue";
import ScrollReveal from "scrollreveal";

export default {
  name: "ProjectList",
  data() {
    return {
      project1: "/img/img01.png",
      project2: "/img/img02.png",
      alt: "projeto website imobiliario",
      alt2: "projeto de amostra de barbearia",
    };
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

      sr.reveal(".content");
    });
  },
};
</script>

<style scoped>
.content {
  padding-top: 100px;
  visibility: hidden;
}

a {
  text-decoration: none;
}

.project {
  margin: 15px 0;
}

.no-gutter .project {
  margin: 0 !important;
  padding: 0 !important;
}

.has-spacer {
  margin-left: 30px;
  margin-right: 30px;
  margin-bottom: 30px;
}

.has-spacer-extra-space {
  margin-left: 30px;
  margin-right: 30px;
  margin-bottom: 30px;
}

.has-side-spacer {
  margin-left: 30px;
  margin-right: 30px;
}

.project-title {
  font-size: 1.25rem;
}

.project-skill {
  font-size: 0.9rem;
  font-weight: 400;
  letter-spacing: 0.06rem;
}

.project-info-box {
  margin: 15px 0;
  background-color: #fff;
  padding: 30px 40px;
  border-radius: 5px;
}

.project-info-box p {
  margin-bottom: 15px;
  padding-bottom: 15px;
  border-bottom: 1px solid #d5dadb;
}

.project-info-box p:last-child {
  margin-bottom: 0;
  padding-bottom: 0;
  border-bottom: none;
}

.hovereffect {
  width: 100%;
  height: 100%;
  float: left;
  overflow: hidden;
  position: relative;
  text-align: center;
  z-index: 2;
}

.hovereffect .overlay {
  width: 100%;
  height: 100%;
  position: absolute;
  overflow: hidden;
  top: 0;
  left: 0;
  opacity: 0;
  background-color: rgba(0, 0, 0, 0.25);
  -webkit-transition: all 0.3s ease-in-out;
  transition: all 0.3s ease-in-out;
  border-radius: 5px;
}

.primary-dark .hovereffect .overlay {
  background-color: rgba(215, 48, 39, 0.95);
}

.white .hovereffect .overlay {
  background-color: rgba(255, 255, 255, 0.75);
}

.dark-overlay .hovereffect .overlay {
  background-color: rgba(0, 0, 0, 0.5);
}

.hovereffect img {
  display: block;
  position: relative;
  -webkit-transition: all 0.3s linear;
  transition: all 0.3s linear;
  border: 10px solid #fff;
  border-radius: 5px;
}

.no-image-border .hovereffect img {
  border: none;
  border-radius: 5px;
}

.no-image-border.no-gutter .hovereffect img,
.no-image-border.no-gutter .hovereffect .overlay {
  border: none;
  border-radius: 0;
}

.hovereffect:hover img {
  -webkit-transform: rotate(-7deg) scale(1.33);
  -ms-transform: rotate(-7deg) scale(1.33);
  transform: rotate(-7deg) scale(1.33);
}

.hovereffect-title .project-title-wrapper {
  position: absolute;
  top: 45%;
  left: 0;
  margin-top: -32px;
  width: 100%;
  padding: 10px;
  -webkit-transition: all 0.5s ease-in-out;
  transition: all 0.5s ease-in-out;
}

.project:hover .hovereffect-title .project-title-wrapper {
  top: 50%;
}

.hovereffect-title .project-title {
  color: #fff;
  background: transparent;
  margin-bottom: 5px;
}

.white .hovereffect-title .project-title {
  color: #171819;
}

.hovereffect-title p {
  color: #fff;
  background: transparent;
  font-size: 12px;
  margin: 0;
}

.white .hovereffect-title p {
  color: #686c6d;
}

.hovereffect-title .hover-icons {
  font-size: 16px;
  background: transparent;
  position: absolute;
  bottom: 10%;
  left: 0;
  right: 0;
  -webkit-transition: all 0.3s ease-in-out;
  transition: all 0.3s ease-in-out;
}

.project:hover .hovereffect-title .hover-icons {
  bottom: 15%;
}

.hovereffect-title .hover-icons a {
  color: #fff;
}

.white .hovereffect-title .hover-icons a {
  color: #171819;
}

.hovereffect-title.project-icons {
  position: absolute;
  right: 0;
  bottom: -10px;
  -webkit-transition: all 0.5s ease-in-out;
  transition: all 0.5s ease-in-out;
}

.project:hover .hovereffect-title.project-icons {
  bottom: 0;
}

.hovereffect-title.project-icons a {
  display: inline-block;
  position: relative;
  color: #fff;
  font-size: 11px;
  line-height: 40px;
  width: 45px;
  height: 38px;
  background: #8e9294;
  opacity: 0.75;
}

.hovereffect-title.project-icons a i {
  margin-right: -2px;
}

.hovereffect-title.project-icons a:first-child {
  background-color: #7c8284;
  margin-right: -4px;
}

.project-icons a:hover,
.project-icons a:first-child:hover {
  background-color: #505254 !important;
  opacity: 1;
}

.hovereffect-title.project-icons .hover-icons {
  color: #fff;
  position: relative;
  top: 0;
  left: 0;
  right: 0;
  margin-top: 0;
  opacity: 1;
}

.hovereffect-title.project-icons a:hover {
  background: #931c19;
}

.primary-dark .project-icons a {
  color: #d73027;
  background-color: #fff;
}

.primary-dark .project-icons a:hover {
  background-color: #efefef;
}

.primary-dark .project-icons a:hover {
  color: #fff;
}

.primary-dark .hovereffect-title.project-icons .hover-icons {
  color: #d73027;
}

.white .hovereffect-title .hover-icons {
  color: #171819;
}

.white .hovereffect-title.project-icons .hover-icons {
  color: #171819;
}

.hovereffect-title .hover-icons a {
  opacity: 0.7;
  margin: 0 4px;
}

.hovereffect-title .hover-icons a {
  opacity: 0.7;
}

.hovereffect-title .hover-icons a:hover {
  opacity: 1;
}

.hovereffect:hover .overlay {
  opacity: 1;
  filter: alpha(opacity=100);
}

.boxed-portfolio .card {
  background-color: #fff;
  -webkit-box-shadow: 0 1px 4px rgba(0, 0, 0, 0.025),
    0 1px 4px rgba(0, 0, 0, 0.05) !important;
  box-shadow: 0 1px 4px rgba(0, 0, 0, 0.025), 0 1px 4px rgba(0, 0, 0, 0.05) !important;
}

.boxed-portfolio .hovereffect img,
.boxed-portfolio .hovereffect .overlay {
  border: none;
  border-bottom-left-radius: 0;
  border-bottom-right-radius: 0;
}

.boxed-portfolio .card-body {
  padding: 25px 30px;
  border-top: 1px solid #efefef;
}
.font-size-16,
.fs-16 {
  font-size: 16px !important;
}
.font-weight-700,
.fw-bold,
.fw-500 {
  font-weight: 700 !important;
}
.card-title {
  margin-bottom: 0;
}
.title-link,
.title-link:focus {
  color: #171819;
}
.boxed-portfolio .card {
  background-color: #fff;
  -webkit-box-shadow: 0 1px 4px rgba(0, 0, 0, 0.025),
    0 1px 4px rgba(0, 0, 0, 0.05) !important;
  box-shadow: 0 1px 4px rgba(0, 0, 0, 0.025), 0 1px 4px rgba(0, 0, 0, 0.05) !important;
}
.mb-0 {
  margin-bottom: 0 !important;
}
.card {
  background-color: transparent;
  border: none;
  border-radius: 5px;
  margin-bottom: 30px;
}
.mt-5 {
  margin-top: 5px !important;
}
.mb-0 {
  margin-bottom: 0 !important;
}
p {
  font-family: "Barlow", sans-serif !important;
  font-weight: 300;
  font-size: 1rem;
  color: #686c6d;
  letter-spacing: 0.03rem;
  margin-bottom: 10px;
}
</style>
