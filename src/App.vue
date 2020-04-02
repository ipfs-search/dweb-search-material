<template>
  <v-app>
    <v-app-bar
      app
      color="#607d8b"
      height="58"
      dark
    >
    <container class="d-flex justify-space-between full-width">

      <div class="d-flex align-center">
        <router-link to="/">
          <v-img
            alt="DWEB Search Logo"
            class="logo shrink mr-3"
            contain
            src="./assets/logo.svg"
            transition="scale-transition"
            width="32"
          />
        </router-link>
        <h2 class="hidden-sm-and-down mr-3">DWEB&#8194;<span>SEARCH</span></h2>
      </div>

      <div class="search d-flex align-center flex-sm-grow-1 flex-sm-shrink-0 flex-xs-shrink-1">
        <v-text-field
          placeholder="Search..."
          flat
          light
          rounded
          autofocus
          validate-on-blur
          hide-details
          solo
          v-model="query"
          @keyup.enter="onClickSearch"
          append-icon="mdi-magnify"
        >
        </v-text-field>
      </div>

      <div class="contra-spacer hidden-md-and-down"></div>

    </container>


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
  .full-width {
    width: 100%;
  }
  .logo {
    opacity: 0.7;
  }
  h2 {
    letter-spacing: 2px;
    font-weight: 600;
    opacity: 0.7;
    span {
      letter-spacing: 3px;
      font-weight: 300;
    }
  }
  .contra-spacer {
    width: 257px;
  }
  // .search {
  //   max-width: 900px;
  // }
</style>

<style lang="scss">
  .v-icon.mdi-magnify {
    font-size: 28px !important;
    margin-right: -18px !important;
  }
  .v-text-field__slot {
    margin-left: -8px !important;
  }
</style>