<template>
  <v-container>
    <v-layout
      text-center
      wrap
    >
      <v-flex
        mb-5
        xs12
      >
        <h2 class="headline font-weight-bold mb-3">{{ msg }}</h2>
      </v-flex>

    </v-layout>
  </v-container>
</template>

<script>
export default {
  name: 'PageDetail',

  props: {
    msg: String,
  },

  data: () => ({

  }),
};
</script>
