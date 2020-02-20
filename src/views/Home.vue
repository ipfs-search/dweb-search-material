<template>
  <div class="home">
    <section>
      <v-parallax src="../assets/background-02.png" height="600" class=parallax>
        <v-layout
          column
          align-center
          justify-center
          class="white--text"
        >
          <h2 class="white--text mb-2 display-1 text-center">Search for the Distributed&#160;Web</h2>
          <div class="subheading mb-4 text-center">Since 2016</div>
          <v-btn
            class="mt-12"
            color="secondary lighten-1"
            dark
            large
            to="/api"
          >
            Show API
          </v-btn>
        </v-layout>
      </v-parallax>
    </section>

    <section>
      <v-layout
        column
        wrap
        class="my-12"
        align-center
      >
        <v-flex xs12 sm4 class="my-4">
          <div >
            <h2 class="display-1 text-center mb-2">The best way to search the distributed web</h2>
            <div class="subheading text-center mb-4">
              Lorem ipsum dolor sit amet consectetur
            </div>
          </div>
        </v-flex>
        <v-flex xs12>
          <v-container grid-list-xl>
            <v-layout row wrap align-center>
              <v-flex xs12 md4>
                <v-card flat class="transparent">
                  <v-card-text class="text-center">
                    <v-icon size="58px" class="secondary--text text--lighten-1">mdi-wrench</v-icon>
                  </v-card-text>
                  <v-card-title primary-title>
                    <div class="headline">Search high volumes of&#160;data</div>
                  </v-card-title>
                  <v-card-text>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Dicta eveniet quae, officiis, iure
                    quam aperiam harum quisquam, esse totam quibusdam animi officia! Laborum ipsum reiciendis
                    asperiores a! Molestiae, illo rem. Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sit
                    fuga sint vero voluptates expedita deleniti ad iste omnis.
                  </v-card-text>
                </v-card>
              </v-flex>
              <v-flex xs12 md4>
                <v-card flat class="transparent">
                  <v-card-text class="text-center">
                    <v-icon size="58px" class="secondary--text text--lighten-1">mdi-flash</v-icon>
                  </v-card-text>
                  <v-card-title primary-title>
                    <div class="headline">Decentralized trust</div>
                  </v-card-title>
                  <v-card-text>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Dicta eveniet quae, officiis, iure
                    quam aperiam harum quisquam, esse totam quibusdam animi officia! Laborum ipsum reiciendis
                    asperiores a! Molestiae, illo rem. Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sit
                    fuga sint vero voluptates expedita deleniti ad iste omnis.
                  </v-card-text>
                </v-card>
              </v-flex>
              <v-flex xs12 md4>
                <v-card flat class="transparent">
                  <v-card-text class="text-center">
                    <v-icon size="58px" class="secondary--text text--lighten-1">mdi-open-source-initiative</v-icon>
                  </v-card-text>
                  <v-card-title primary-title>
                    <div class="headline">Open Sourced</div>
                  </v-card-title>
                  <v-card-text>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Dicta eveniet quae, officiis, iure
                    quam aperiam harum quisquam, esse totam quibusdam animi officia! Laborum ipsum reiciendis
                    asperiores a! Molestiae, illo rem. Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sit
                    fuga sint vero voluptates expedita deleniti ad iste omnis.
                  </v-card-text>
                </v-card>
              </v-flex>
            </v-layout>
          </v-container>
        </v-flex>
      </v-layout>
    </section>

    <PageDetail msg=""/>
  </div>
</template>

<script>
// @ is an alias to /src
import PageDetail from '@/components/PageDetail.vue';

export default {
  name: 'home',
  components: {
    PageDetail
  },
};
</script>

<style scoped lang="scss">

.parallax {
  background-color: darken(#607d8b, 10%);
  // background-color: #0e3344;
}

.text-center {
  margin-left: -12px;
}

</style>




