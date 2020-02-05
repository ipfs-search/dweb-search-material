<template>
  <v-app>
    <v-app-bar
      app
      color="#607d8b"
      height="64"
      dark
    >
      <div class="d-flex align-center">
        <router-link to="/">
          <v-img
            alt="Vuetify Logo"
            class="shrink mr-3"
            contain
            src="./assets/logo.svg"
            transition="scale-transition"
            width="42"
          />
        </router-link>
        <h2 class="hidden-sm-and-down">DWEB&#8194;<span>SEARCH</span></h2>
      </div>

      <v-spacer class="hidden-sm-and-down"></v-spacer>

        <v-text-field
          placeholder="Search..."
          flat
          dark
          hide-details
          solo-inverted
          v-model="query"
          @keyup.enter="onClickSearch"
        >
          <template v-slot:append-outer>
            <v-icon
              size="32px"
              @click="onClickSearch"
            >mdi-magnify</v-icon>
          </template>
        </v-text-field>

    </v-app-bar>

    <v-content>
      <router-view></router-view>
    </v-content>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    query: null,
    previousQuery: null,
  }),

  methods: {
    onClickSearch() {
      if (this.previousQuery !== this.query) {
        this.$router.push({ path: `/results/${this.query}` });
      }
      this.previousQuery = this.query;
    },

    watchRouter() {
      if (this.$route.name === 'home') {
        this.query = '';
      }
    }
  },

  watch: {
    '$route': 'watchRouter'
  },

};
</script>

<style scoped lang="scss">
  h2 {
    letter-spacing: 2px;
    font-weight: 600;
    span {
      letter-spacing: 3px;
      font-weight: 300;
    }
  }
</style>