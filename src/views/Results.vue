<template>
  <div class="results">
    <!-- <PageDetail msg="This is an example of the results page"/>
    <div>
      You've searched for {{ query }}
    </div> -->
    <v-container class="mx-auto pa-0 pt-4">
      <v-container class="mt-n3 mb-n6">
        <v-row justify="end">
          <v-col cols="12" class="pb-0 mb-0">
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

      <v-subheader class="mt-n2">August</v-subheader>
      <v-list three-line class="mt-n2 mb-2">
        <template v-for="(item, index) in entrees">
          <v-divider
            v-if="item.divider"
            :key="index"
            :inset="item.inset"
          ></v-divider>

          <v-list-item
            v-else
            :key="item.title"
            @click="doSomething"
          >

            <v-list-item-content>
              <v-list-item-title v-html="item.title"></v-list-item-title>
              <v-list-item-subtitle v-html="item.subtitle"></v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </template>
      </v-list>

      <v-subheader>Grouped objects</v-subheader>
      <v-item-group multiple class="mt-n6">
        <v-container>
          <v-row>
            <v-col
              v-for="n in 6"
              :key="n"
              cols="6"
              sm="4"
              md="3"
              lg="2"
            >
              <v-item v-slot:default="{ active, toggle }">
                <v-card
                  :color="active ? 'primary' : ''"
                  class="d-flex align-center"
                  dark
                  height="200"
                  @click="toggle"
                >
                  <v-scroll-y-transition>
                    <div
                      v-if="active"
                      class="display-3 flex-grow-1 text-center"
                    >
                      Active
                    </div>
                  </v-scroll-y-transition>
                </v-card>
              </v-item>
            </v-col>
          </v-row>
        </v-container>
      </v-item-group>


      <v-subheader>May</v-subheader>
      <v-container fluid class="mt-n6">
        <v-row>
          <v-col
            v-for="i in 6"
            :key="i"
            cols="6"
            sm="4"
            md="3"
            lg="2"
          >
            <img
              :src="`https://randomuser.me/api/portraits/men/${i + 20}.jpg`"
              alt="lorem"
              class="image"
              height="100%"
              width="100%"
            >
          </v-col>
        </v-row>
      </v-container>

      <v-subheader>June</v-subheader>
      <v-container fluid class="mt-n6">
        <v-row>
          <v-col
            v-for="i in 6"
            :key="i"
            cols="6"
            sm="4"
            md="3"
            lg="2"
          >
            <img
              :src="`https://randomuser.me/api/portraits/women/${i + 5}.jpg`"
              alt="lorem"
              class="image"
              height="100%"
              width="100%"
            >
          </v-col>
        </v-row>
      </v-container>

      <v-subheader>August</v-subheader>
      <v-container fluid class="mt-n6">
        <v-row>
          <v-col
            v-for="n in 9"
            :key="n"
            class="d-flex child-flex"
            cols="6"
            sm="4"
            md="3"
            lg="2"
          >
            <v-card flat tile class="d-flex">
              <v-img
                :src="`https://picsum.photos/500/300?image=${n * 5 + 10}`"
                :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}`"
                aspect-ratio="1"
                class="grey lighten-2"
              >
                <template v-slot:placeholder>
                  <v-row
                    class="fill-height ma-0"
                    align="center"
                    justify="center"
                  >
                    <v-progress-circular indeterminate color="grey lighten-5"></v-progress-circular>
                  </v-row>
                </template>
              </v-img>
            </v-card>
          </v-col>
        </v-row>
      </v-container>

      <template >
        <div class="mt-4">
          <v-pagination
            v-model="page"
            :length="15"
            :total-visible="7"
          ></v-pagination>
        </div>
      </template>

      <template>
        <v-footer min-height="36px" color="white">
          <v-spacer></v-spacer>
          <div></div>
        </v-footer>
      </template>

    </v-container>
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
    entrees: [
      { divider: true },
      {
        avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg',
        title: 'Brunch this weekend?',
        subtitle: "<span class='text--primary'>Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?",
      },
      { divider: true },
      {
        avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg',
        title: 'Summer BBQ <span class="grey--text text--lighten-1">4</span>',
        subtitle: "<span class='text--primary'>to Alex, Scott, Jennifer</span> &mdash; Wish I could come, but I'm out of town this weekend.",
      },
      { divider: true },
      {
        avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg',
        title: 'Oui oui',
        subtitle: "<span class='text--primary'>Sandra Adams</span> &mdash; Do you have Paris recommendations? Have you ever been?",
      },
      { divider: true },
    ],

    selectedSearchableCategories: [],

    searchableCategories: [
      'Texts',
      'Images',
      'Music',
      'Videos',
      'Directories',
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

</style>