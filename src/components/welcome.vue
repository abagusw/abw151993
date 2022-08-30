<template>
  <v-container>
    <v-card>
      <v-row>
        <v-col class="">
          <div class="d-flex justify-center">
            <span class="red--text">Hallo Welcome to ABW E-Banking</span>
          </div>
        </v-col>
      </v-row>
      <v-row class="mt-2 mb-3">
        <v-col>
          <div class="d-flex justify-center">
            <v-btn color="success" @click="this.$router.push({ name: 'login' })">Login to continue</v-btn>
          </div>
        </v-col>
      </v-row>
    </v-card>
  </v-container>
</template>
