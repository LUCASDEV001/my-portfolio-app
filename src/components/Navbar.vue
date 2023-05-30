<template>
  <!-- Navbar -->
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark fixed-top">
    <div class="container-fluid">
      <a class="navbar-brand fs-4" id="nav-logo" href="/">LUCAS CAVALCANTE</a>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
        :class="{ collapsed: !isOpen }"
        @click="toggleNavbar"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mb-2 mb-lg-0 ms-auto fs-5">
          <li class="nav-item" :class="{ active: isActive('/') }">
            <router-link
              to="/"
              class="nav-link"
              aria-current="page"
              @click="closeNavbar"
              >Início</router-link
            >
          </li>

          <li class="nav-item" :class="{ active: isActive('/services') }">
            <router-link to="/services" class="nav-link" @click="closeNavbar"
              >Serviços</router-link
            >
          </li>

          <li class="nav-item" :class="{ active: isActive('/projects') }">
            <router-link to="/projects" class="nav-link" @click="closeNavbar"
              >Projetos</router-link
            >
          </li>

          <li class="nav-item" :class="{ active: isActive('/contact') }">
            <router-link to="/contact" class="nav-link" @click="closeNavbar"
              >Contato</router-link
            >
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      isOpen: false,
    };
  },
  methods: {
    toggleNavbar() {
      const navbar = document.querySelector(".navbar-collapse");
      const isCollapsed = navbar.classList.contains("show");

      if (isCollapsed) {
        navbar.classList.remove("show");
      } else {
        navbar.classList.add("show");
      }
    },
    closeNavbar() {
      const navbar = document.querySelector(".navbar-collapse");
      if (navbar.classList.contains("show")) {
        navbar.classList.remove("show");
      }
    },
    isActive(route) {
      return this.$route.path === route;
    },
  },
};
</script>

<style scoped>
nav {
  height: 80px;
  font-weight: 700;
  padding-left: 40px;
  padding-right: 40px;
  z-index: 1000;
}

#nav-logo {
  font-family: "Patua One", cursive;
  user-select: none;
}

#nav-logo:hover {
  color: #ffca2c;
  transition: 0.5s;
}

.navbar-nav .nav-item.active .nav-link {
  color: #ffca2c;
}

@media (max-width: 768px) {
  .navbar-nav {
    margin-top: 30px;
    border: 2px solid #ffca2c;
    border-radius: 5px;
  }

  .navbar-nav .nav-item {
    background-color: #333;
    text-align: center;
    padding: 10px;
  }
}

@media (max-width: 368px) {
  #nav-logo {
    display: none;
  }
}
</style>
