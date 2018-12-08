<template>
  <div id="app">
    <nav class="navbar is-transparent">
      <div class="container">
        <!-- logo -->
        <div class="navbar-brand">
          <a class="navbar-item">MyCompany</a>
          <!-- hamburger icon -->
          <span
            class="navbar-burger"
            v-on:click="toggleNav"
            v-bind:class="{ 'is-active': isActive }"
          >
            <span></span>
            <span></span>
            <span></span>
          </span>
        </div>
        <!-- menu -->
        <div
          class="navbar-menu"
          v-bind:class="{ 'is-active': isActive }"
        >
          <div class="navbar-end">
            <router-link to="/" class="navbar-item r-item">Home</router-link>
            <router-link to="faq" class="navbar-item r-item">Features</router-link>
            <router-link to="faq" class="navbar-item r-item">About</router-link>
            <router-link to="faq" class="navbar-item r-item">FAQ</router-link>
            <div class="navbar-item">
              <p class="control">
                <a class="button is-primary is-outlined">
                  <span class="icon">
                    <i class="fa fa-download"></i>
                  </span>
                  <span>
                    Join Now
                  </span>
                </a>
              </p>
            </div>
          </div>
        </div>
      </div>
    </nav>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App',
  data: function () {
    return {
      isActive: false
    }
  },
  methods: {
    toggleNav: function () {
      this.isActive = !this.isActive
    }
  }
}
</script>

<style lang="sass">
@import '../node_modules/bulma/bulma.sass'
@import 'mq'

.navbar
  background-color: #383838
  a:hover
    color: gray

.navbar-brand a
  color: #fff
  font-weight: bold

a.r-item
  color: #c1c1c1
  padding: 0.5rem 1.75rem
  +mobile
    color: gray
    &:hover
      background-color: #f1f1f1

.navbar-burger span
  background-color: #c1c1c1

.navbar-burger:hover
  background-color: #f1f1f1;

</style>
