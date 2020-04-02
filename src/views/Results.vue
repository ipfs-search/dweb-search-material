<template>
  <div class="results">
    <!-- <PageDetail msg="This is an example of the results page"/>
    <div>
      You've searched for {{ query }}
    </div> -->
    <v-container class="mx-auto pa-0 pt-4">
      <v-container class="mt-n3 mb-n6">
        <v-row justify="end">
          <v-col cols="12" class="result-header mb-n6 pb-0 mb-0">
            <p class="text-right">We found 4320 results in 288 pages!</p>
          </v-col>
          <v-col cols="12" class="pb-0 mb-n2">
            <v-select
              v-model="selectedSearchableCategories"
              :items="searchableCategories"
              label="Filter search"
              outlined
              chips
              small-chips
              deletable-chips
              multiple
            >
              <template v-slot:prepend-item>
                <v-list-item
                  ripple
                  @click="toggle"
                >
                  <v-list-item-action>
                    <v-icon :color="selectedSearchableCategories.length > 0 ? 'indigo darken-4' : ''">{{ icon }}</v-icon>
                  </v-list-item-action>
                  <v-list-item-content>
                    <v-list-item-title>Select All</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-divider class="mt-2"></v-divider>
              </template>
            </v-select>
          </v-col>
        </v-row>
      </v-container>

      <v-container>
        <v-row dense>
          <v-col cols="12">
            <v-subheader class="mt-n2 mb-n4">Texts (230) - view all</v-subheader>
          </v-col>
        </v-row>
        <v-row dense>
          <v-col cols="12">
            <v-card>
              <v-card-title class="subtitle-1">Unlimited music now</v-card-title>

              <v-card-subtitle>Listen to your favorite artists and albums whenever and wherever, online and offline.</v-card-subtitle>

              <!-- <v-card-actions>
                <v-btn text>Listen Now</v-btn>
              </v-card-actions> -->
            </v-card>
          </v-col>
          <v-col cols="12">
            <v-card>
              <v-card-title class="subtitle-1">Unlimited music now</v-card-title>

              <v-card-subtitle>Listen to your favorite artists and albums whenever and wherever, online and offline.</v-card-subtitle>

              <!-- <v-card-actions>
                <v-btn text>Listen Now</v-btn>
              </v-card-actions> -->
            </v-card>
          </v-col>
          <v-col cols="12">
            <v-card>
              <v-card-title class="subtitle-1">Unlimited music now</v-card-title>

              <v-card-subtitle>Listen to your favorite artists and albums whenever and wherever, online and offline.</v-card-subtitle>

              <!-- <v-card-actions>
                <v-btn text>Listen Now</v-btn>
              </v-card-actions> -->
            </v-card>
          </v-col>
          <v-col cols="12">
            <v-subheader class="mt-n2 mb-n4"></v-subheader>
          </v-col>
        </v-row>
      </v-container>

      <v-container>
        <v-row dense>
          <v-col cols="12">
            <v-subheader class="mt-n2 mb-n4">Audio (40)</v-subheader>
          </v-col>
        </v-row>
        <v-row dense>
          <v-col cols="12">
            <v-card>
              <div class="d-flex flex-no-wrap justify-space-between">
                <div>
                  <v-card-title
                    class="subtitle-1"
                  >Supermodel</v-card-title>
                  <v-card-subtitle>Foster the People</v-card-subtitle>
                </div>
                <v-avatar
                  class="ma-2"
                  size="125"
                  tile
                >
                  <v-img src="https://cdn.vuetifyjs.com/images/cards/halcyon.png"></v-img>
                </v-avatar>
              </div>
            </v-card>
          </v-col>
          <v-col cols="12">
            <v-card>
              <div class="d-flex flex-no-wrap justify-space-between">
                <div>
                  <v-card-title
                    class="subtitle-1"
                  >Halcyon Days</v-card-title>

                  <v-card-subtitle>Ellie Goulding</v-card-subtitle>
                </div>

                <v-avatar
                  class="ma-2"
                  size="125"
                  tile
                >
                  <v-img src="https://cdn.vuetifyjs.com/images/cards/foster.jpg"></v-img>
                </v-avatar>
              </div>
            </v-card>
          </v-col>
          <v-col cols="12">
            <v-card>
              <div class="d-flex flex-no-wrap justify-space-between">
                <div>
                  <v-card-title
                    class="subtitle-1"
                  >Supermodel</v-card-title>
                  <v-card-subtitle>Foster the People</v-card-subtitle>
                </div>
                <v-avatar
                  class="ma-2"
                  size="125"
                  tile
                >
                  <v-img src="https://cdn.vuetifyjs.com/images/cards/halcyon.png"></v-img>
                </v-avatar>
              </div>
            </v-card>
          </v-col>
        </v-row>
      </v-container>

      <template>
        <v-footer min-height="36px" color="white">
          <v-spacer></v-spacer>
          <div></div>
        </v-footer>
      </template>

    </v-container>

    <template >
      <div class="mt-4 mb-8">
        <v-pagination
          v-model="page"
          :length="15"
          :total-visible="7"
        ></v-pagination>
      </div>
    </template>
  </div>
</template>

<script>
import PageDetail from '@/components/PageDetail.vue';
export default {
  name: 'results',
  components: {
    // eslint-disable-next-line vue/no-unused-components
    PageDetail,
  },

  created () {
    this.fetchData()
  },

  data: () => ({
    page: 1,
    query: null,
    // entrees: [
    //   { divider: true },
    //   {
    //     avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg',
    //     title: 'Brunch this weekend?',
    //     subtitle: "<span class='text--primary'>Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?",
    //   },
    //   { divider: true },
    //   {
    //     avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg',
    //     title: 'Summer BBQ <span class="grey--text text--lighten-1">4</span>',
    //     subtitle: "<span class='text--primary'>to Alex, Scott, Jennifer</span> &mdash; Wish I could come, but I'm out of town this weekend.",
    //   },
    //   { divider: true },
    //   {
    //     avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg',
    //     title: 'Oui oui',
    //     subtitle: "<span class='text--primary'>Sandra Adams</span> &mdash; Do you have Paris recommendations? Have you ever been?",
    //   },
    //   { divider: true },
    // ],

    selectedSearchableCategories: [],

    searchableCategories: [
      'Texts (230)',
      'Images (741)',
      'Music (40)',
      'Videos (25)',
      'Directories (400)',
    ],
  }),

  watch: {
    '$route': 'fetchData'
  },

  computed: {
      likesAllSearchableCategories () {
        return this.selectedSearchableCategories.length === this.searchableCategories.length
      },
      likesSomeSearchableCategories () {
        return this.selectedSearchableCategories.length > 0 && !this.likesAllSearchableCategories
      },
      icon () {
        if (this.likesAllSearchableCategories) return 'mdi-close-box'
        if (this.likesSomeSearchableCategories) return 'mdi-minus-box'
        return 'mdi-checkbox-blank-outline'
      },
  },

  methods: {
    toggle () {
      this.$nextTick(() => {
        if (this.likesAllSearchableCategories) {
          this.selectedSearchableCategories = []
        } else {
          this.selectedSearchableCategories = this.searchableCategories.slice()
        }
      })
    },

    fetchData() {
      this.query = this.$route.params.query;
    },

    doSomething() {
      // eslint-disable-next-line no-console
      console.log('You\'ve clicked');
    },
  }
};
</script>

<style scoped lang="scss">
  .results {
    .result-header {
      p {
        font-size: 80%;
        opacity: 0.6;
      }
    }
  }
</style>