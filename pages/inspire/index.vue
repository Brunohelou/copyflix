<template>
  <v-row>
    <v-col class="text-center">
      <v-sheet
    class="mx-auto"
    max-width="700"
  >
    <v-slide-group
      multiple
      show-arrows
    >
      <v-slide-item
        v-for="n in 25"
        :key="n"
        v-slot="{ active, toggle }"
      >
        <v-btn
          class="mx-2"
          :input-value="active"
          active-class="purple white--text"
          depressed
          rounded
          @click="toggle"
        >
          Options {{ n }}
        </v-btn>
      </v-slide-item>
    </v-slide-group>
  </v-sheet>
    </v-col>
  </v-row>
</template>
