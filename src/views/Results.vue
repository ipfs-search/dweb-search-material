<template>
  <div class="results">
    <!-- <PageDetail msg="This is an example of the results page"/>
    <div>
      You've searched for {{ query }}
    </div> -->
    <v-container class="mx-auto pa-0 pt-2">

      <v-col cols="12" class="pb-0">
        <v-select
          class="mb-0"
          v-model="select"
          :items="items"
          label="Filter search"
          outlined
          chips
          small-chips
          deletable-chips
          multiple
        ></v-select>
      </v-col>
      <v-list three-line>
        <template v-for="(item, index) in entrees">
          <v-subheader
            v-if="item.header"
            :key="item.header"
            v-text="item.header"
          ></v-subheader>

          <v-divider
            v-else-if="item.divider"
            :key="index"
            :inset="item.inset"
          ></v-divider>

          <v-list-item
            v-else
            :key="item.title"
            @click="doSomething"
          >
            <!-- <v-list-item-avatar>
              <v-img :src="item.avatar"></v-img>
            </v-list-item-avatar> -->

            <v-list-item-content>
              <v-list-item-title v-html="item.title"></v-list-item-title>
              <v-list-item-subtitle v-html="item.subtitle"></v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </template>
      </v-list>


      <v-card
        class="mx-auto"
        max-width="344"
        outlined
      >
        <v-list-item three-line>
          <v-list-item-content>
            <div class="overline mb-4">OVERLINE</div>
            <v-list-item-title class="headline mb-1">Headline 5</v-list-item-title>
            <v-list-item-subtitle>Greyhound divisely hello coldly fonwderfully</v-list-item-subtitle>
          </v-list-item-content>

          <v-list-item-avatar
            tile
            size="80"
            color="grey"
          ></v-list-item-avatar>
        </v-list-item>

        <v-card-actions>
          <v-btn text>Button</v-btn>
          <v-btn text>Button</v-btn>
        </v-card-actions>
      </v-card>

      <v-subheader>May</v-subheader>
        <v-container fluid>
          <v-row>
            <v-col
              v-for="i in 6"
              :key="i"
              cols="2"
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
        <v-container fluid>
          <v-row>
            <v-col
              v-for="i in 6"
              :key="i"
              cols="2"
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
    query: null,
    entrees: [
        { header: 'Texts' },
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
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/4.jpg',
          title: 'Birthday gift',
          subtitle: "<span class='text--primary'>Trevor Hansen</span> &mdash; Have any ideas about what we should get Heidi for her birthday?",
        },
        { divider: true },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/5.jpg',
          title: 'Recipe to try',
          subtitle: "<span class='text--primary'>Britta Holt</span> &mdash; We should eat this: Grate, Squash, Corn, and tomatillo Tacos.",
        },
      ],
      select: ['Texts', 'Music'],
      items: [
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

  methods: {
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