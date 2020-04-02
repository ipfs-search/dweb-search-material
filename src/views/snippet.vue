<template>
  <div>
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
  </div>
</template>


