<template>
  <header class="header-global">
    <nav
      id="navbar-main"
      class="navbar navbar-main navbar-expand-lg navbar-transparent navbar-light"
    >
      <div class="container">
        <router-link to="/" class="navbar-brand mr-lg-5"
          ><img
            src="../../../public/frontend/img/brand/white.png"
            style="width: 200px; height: inherit"
        /></router-link>

        <button
          class="navbar-toggler"
          type="button"
          data-toggle="collapse"
          data-target="#navbar_global"
          aria-controls="navbar_global"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="navbar-collapse collapse" id="navbar_global">
          <div class="navbar-collapse-header">
            <div class="row">
              <div class="col-6 collapse-brand">
                <router-link to="/"
                  ><img
                    src="../../../public/frontend/img/brand/blue.png"
                    style="width: 300px; height: inherit"
                /></router-link>
              </div>
              <div class="col-6 collapse-close">
                <button
                  type="button"
                  class="navbar-toggler"
                  data-toggle="collapse"
                  data-target="#navbar_global"
                  aria-controls="navbar_global"
                  aria-expanded="false"
                  aria-label="Toggle navigation"
                >
                  <span></span>
                  <span></span>
                </button>
              </div>
            </div>
          </div>
          <ul class="navbar-nav navbar-nav-hover align-items-lg-center">
            <li class="nav-item dropdown">
              <a href="#" class="nav-link" data-toggle="dropdown" role="button">
                <i class="ni ni-collection d-lg-none"></i>
                <span class="nav-link-inner--text">Pages</span>
              </a>
              <div class="dropdown-menu">
                <router-link to="/profile" class="dropdown-item"
                  >Profile</router-link
                >
                <router-link to="/login" class="dropdown-item"
                  >Sign In
                </router-link>
                <router-link to="/register" class="dropdown-item"
                  >Register</router-link
                >
              </div>
            </li>
          </ul>
          <ul class="navbar-nav align-items-lg-center ml-lg-auto">
            <li class="nav-item d-none d-lg-block ml-lg-4">
              <router-link
                to="/logIn"
                target="_blank"
                class="btn btn-neutral btn-icon"
                ><span class="nav-link-inner--text">Sign In</span></router-link
              >
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </header>
</template>
<script>
export default {
  name: "AppHeader",
};
</script>