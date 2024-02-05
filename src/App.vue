<template>
  <v-app theme="">
    <v-navigation-drawer v-model="isDrawerOpen">
     <v-list>
      <v-list-subheader>Menu</v-list-subheader>
      <v-list-item prepend-icon="mdi-home">Home</v-list-item>
      <v-list-item prepend-icon="mdi-account">Usuários</v-list-item>

      <v-list-group value="Clientes">
        <template #activator="{ props }">
          <v-list-item
            v-bind="props"
            prepend-icon="mdi-account-circle"
            title="Clientes"
          ></v-list-item>
        </template>
        <v-list-item prepend-icon="mdi-currency-usd">Faturamento</v-list-item>
        <v-list-item prepend-icon="mdi-chart-line">Relatórios</v-list-item>
      </v-list-group>
     </v-list>
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

        <v-menu>
          <template #activator="{ props }">
            <v-avatar v-bind="props"> 
              <v-img
              src="https://img.freepik.com/fotos-premium/avatar-mulher-geek-furiosa_949597-34.jpg?w=740"
              cover
              ></v-img>
            </v-avatar>
          </template>
          
          <v-card min-width="200px">
            <v-list nav density="compact" :lines="false">
              <v-list-item prepend-icon="mdi-account-outline">
                <v-list-item-title>Meu perfil</v-list-item-title>
              </v-list-item>
              
              <v-list-item prepend-icon="mdi-heart-outline">
                <v-list-item-title>Favoritos</v-list-item-title>
              </v-list-item>
            </v-list>
          </v-card>
        </v-menu>
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
