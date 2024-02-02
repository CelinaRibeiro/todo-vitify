<template>
  <v-app theme="dark">
    <v-navigation-drawer v-model="isDrawerOpen">
      menu
    </v-navigation-drawer>

    <v-app-bar flat class="border-b" @click="isDrawerOpen = !isDrawerOpen">
      <v-app-bar-nav-icon></v-app-bar-nav-icon>
      <v-app-bar-title>Meu App</v-app-bar-title>
     
      <template v-slot:append>
        <v-btn icon class="mr-2">
          <v-badge dot color="info">
            <v-icon icon="mdi-bell-outline"></v-icon>
          </v-badge>
        </v-btn>
        <v-avatar>
          <v-img
          src="https://img.freepik.com/fotos-premium/avatar-mulher-geek-furiosa_949597-34.jpg?w=740"
          cover
          ></v-img>
        </v-avatar>
      </template>
      
    </v-app-bar>
    
    <v-main>
      <v-container>
        <h1>Dashboard</h1>
        <v-row>
          <v-col cols="12" sm="6" md="4">
            <v-card flat class="border">
              <v-img
                class="align-end text-white"
                height="200"
                src="https://images.pexels.com/photos/16842374/pexels-photo-16842374/free-photo-of-praia-litoral-brasil-cidade.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1"
                cover
                > 
                <v-card-title>Top 10 Praia na Bahia</v-card-title>
              </v-img>
              <v-card-subtitle class="pt-4">Salvador</v-card-subtitle>
              <v-card-text>
                <div>Stella Maris</div>
                <div>lorem ipsum dolor sit amet, consectetur</div>
              </v-card-text>
              <v-card-actions>
                <v-btn variant="outlined" color="primary">Ver mais</v-btn>
                <v-btn prepend-icon="mdi-cart" variant="tonal" color="blue">Comprar</v-btn>
              </v-card-actions>
            </v-card>
          </v-col>

          <v-col cols="12" sm="6" md="4">
            <v-card flat class="border">
              <v-img
                class="align-end text-white"
                height="200"
                src="https://images.pexels.com/photos/8319468/pexels-photo-8319468.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1"
                cover
                > 
                <v-card-title>Top 10 Praia na Bahia</v-card-title>
              </v-img>
              <v-card-subtitle class="pt-4">Salvador</v-card-subtitle>
              <v-card-text>
                <div>Rio Vermelho</div>
                <div>lorem ipsum dolor sit amet, consectetur</div>
              </v-card-text>
              <v-card-actions>
                <v-btn variant="outlined" color="primary">Ver mais</v-btn>
                <v-btn prepend-icon="mdi-cart" variant="tonal" color="blue">Comprar</v-btn>
              </v-card-actions>
            </v-card>
          </v-col>

          <v-col cols="12" sm="6" md="4">
            <v-card flat class="border">
              <v-img
                class="align-end text-white"
                height="200"
                src="https://images.pexels.com/photos/16842378/pexels-photo-16842378/free-photo-of-praia-litoral-brasil-cidade.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1"
                cover
                > 
                <v-card-title>Top 10 Praia na Bahia</v-card-title>
              </v-img>
              <v-card-subtitle class="pt-4">Salvador</v-card-subtitle>
              <v-card-text>
                <div>Farol da Barra</div>
                <div>lorem ipsum dolor sit amet, consectetur</div>
              </v-card-text>
              <v-card-actions>
                <v-btn variant="outlined" color="primary">Ver mais</v-btn>
                <v-btn prepend-icon="mdi-cart" variant="tonal" color="blue">Comprar</v-btn>
              </v-card-actions>
            </v-card>
          </v-col>

          <v-col cols="12" sm="6" md="4">
            <v-card flat class="border">
              <v-img
                class="align-end text-white"
                height="200"
                src="https://images.pexels.com/photos/16842378/pexels-photo-16842378/free-photo-of-praia-litoral-brasil-cidade.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1"
                cover
                > 
                <v-card-title>Top 10 Praia na Bahia</v-card-title>
              </v-img>
              <v-card-subtitle class="pt-4">Salvador</v-card-subtitle>
              <v-card-text>
                <div>Farol da Barra</div>
                <div>lorem ipsum dolor sit amet, consectetur</div>
              </v-card-text>
              <v-card-actions>
                <v-btn variant="outlined" color="primary">Ver mais</v-btn>
                <v-btn prepend-icon="mdi-cart" variant="tonal" color="blue">Comprar</v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script setup>
import { ref } from "vue";

  const isDrawerOpen = ref(false);
</script>
