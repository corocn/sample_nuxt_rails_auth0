<template>
  <section class="container">
    <div>
      <div v-if="loggedIn()" class="content">
        <h2>ログイン中です</h2>
          <nuxt-link class="button is-warning" to="/logout">
            <span class="icon"><i class="fa fa-sign-out"></i></span>
            <span>Logout</span>
          </nuxt-link>
      </div>
      <div v-if="!loggedIn()" class="content"> <h2>ログインしてください</h2>
        <nuxt-link class="button is-primary" to="/login">
          <span class="icon"><i class="fa fa-sign-in"></i></span>
          <span>Login</span>
        </nuxt-link>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  methods: {
    loggedIn() {
        return this.$auth0.isAuthenticated();
    }
  }
};
</script>