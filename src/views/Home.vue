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
              Distributed search for the next generation internet
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
                    <div class="headline">Publicly available search</div>
                  </v-card-title>
                  <v-card-text>
                    We wish to provide publicly available search and discovery services in the interest of our users,
                    funded through donations and/or subscriptions and/or opt-in advertisements. This would allow us
                    to sustain ourselves while being able to provide public search functionality for free.
                  </v-card-text>
                </v-card>
              </v-flex>
              <v-flex xs12 md4>
                <v-card flat class="transparent">
                  <v-card-text class="text-center">
                    <v-icon size="58px" class="secondary--text text--lighten-1">mdi-share-variant</v-icon>
                  </v-card-text>
                  <v-card-title primary-title>
                    <div class="headline">External organisations</div>
                  </v-card-title>
                  <v-card-text>
                    We recognise that the expertise and team spirit attained during the development of the
                    public service can be harnessed to implement similar services for external organisations,
                    specifically by providing private search through private clouds and/or ipfs clusters.
                  </v-card-text>
                </v-card>
              </v-flex>
              <v-flex xs12 md4>
                <v-card flat class="transparent">
                  <v-card-text class="text-center">
                    <v-icon size="58px" class="secondary--text text--lighten-1">mdi-earth</v-icon>
                  </v-card-text>
                  <v-card-title primary-title>
                    <div class="headline">Next generation internet</div>
                  </v-card-title>
                  <v-card-text>
                    In the long run, we aspire to scale out and implement truly decentralised/distributed search for the
                    next generation internet, providing strong guarantees for the integrity of the service, meeting the
                    interests ofthe users as well as the openness of our architecture and data.
                  </v-card-text>
                </v-card>
              </v-flex>
            </v-layout>
          </v-container>
        </v-flex>
      </v-layout>
    </section>

    <section>
      <v-parallax src="../assets/background-03.png" height="600" class=parallax>
        <v-layout
          column
          align-center
          justify-center
          class="white--text"
        >
          <!-- <h2 class="white--text mb-2 display-1 text-center">Searching the Univers&#160;since 2016</h2> -->
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
            <h2 class="display-1 text-center mb-2">Search for the Distributed Web Objectives</h2>
          </div>
        </v-flex>
        <v-flex xs12>
          <v-container grid-list-xl>
            <v-layout row wrap align-top>
              <v-flex xs12 md4>
                <v-card flat class="transparent">
                  <v-card-text class="text-center">
                    <v-icon size="58px" class="secondary--text text--lighten-1">mdi-open-source-initiative</v-icon>
                  </v-card-text>
                  <v-card-title primary-title>
                    <div class="headline">World class documentation</div>
                  </v-card-title>
                  <v-card-text>
                    It is our personal experience that many FOSS projects become overly dependent on a very select group of developers, effectively creating a closed community. Besides being approachable and actively engaging in conversations, documentation is a key component to enable others to contribute to a project, improving upon it, using it pinpointing essential mistakes.
                  </v-card-text>
                </v-card>
              </v-flex>
              <v-flex xs12 md4>
                <v-card flat class="transparent">
                  <v-card-text class="text-center">
                    <v-icon size="58px" class="secondary--text text--lighten-1">mdi-account-multiple</v-icon>
                  </v-card-text>
                  <v-card-title primary-title>
                    <div class="headline">Pragmatic solution</div>
                  </v-card-title>
                  <v-card-text>
                    Since its very inception, we wanted to create a search engine that was explicitly open with regards to its intellectual property. As a part of this, we have repeatedly attempted to automatically publish snapshots of our index to the IPFS. We have yet to find a pragmatic solution. We are confident that during the scope of this project, we will be able to publish our full index to IPFS such that others may fork our project.
                  </v-card-text>
                </v-card>
              </v-flex>
              <v-flex xs12 md4>
                <v-card flat class="transparent">
                  <v-card-text class="text-center">
                    <v-icon size="58px" class="secondary--text text--lighten-1">mdi-flash</v-icon>
                  </v-card-text>
                  <v-card-title primary-title>
                    <div class="headline">Darker visions</div>
                  </v-card-title>
                  <v-card-text>
                    Like many who recognise themselves as part of a freedom-loving community, we have harboured the dream of the internet as a truly liberating architecture. Like many, we also have darker visions wherein current tendencies commodify our most intimate identity and our behaviour. We feel that the only true solution to this is to fully distribute the internet’s architecture. We feel that this is possible theoretically, as well as practically.
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




