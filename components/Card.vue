<template>
  <v-card
      class="mx-auto mb-2"
      max-width="344"
      color="#f9f9f9"
      outlined
  >
    <v-img
        src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
        height="200px"
        class="mt-n8"
    ></v-img>

    <v-card-title>
      StemLink
    </v-card-title>

    <v-card-subtitle>
      1,000 miles of wonder
    </v-card-subtitle>

    <v-card-subtitle>
      <v-chip-group
          v-model="selection"
          active-class="deep-purple accent-4 white--text"
          column
      >
        <v-chip>Vue</v-chip>

        <v-chip>Laravel</v-chip>

        <v-chip>Nuxt</v-chip>

        <v-chip>Chrome</v-chip>
      </v-chip-group>
    </v-card-subtitle>

    <v-card-actions>
      <v-btn
          color="orange lighten-2"
          text
      >
        Explore
      </v-btn>

      <v-spacer></v-spacer>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  data: () => ({
    show: false,
  }),
}
</script>