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

        <!-- <v-card flat class="border mb-4">
          <div class="d-flex justify-space-between">
            <v-card-title>Últimos usuários</v-card-title>
            <v-card-title>
              <v-dialog width="600px">
                <template #activator="{ props }">
                  <v-btn v-bind="props" variant="tonal" size="small">Adicionar usuário</v-btn>
                </template>

                <v-card>
                  <v-card-text>ok ok</v-card-text>
                </v-card>
              </v-dialog>
            </v-card-title>
          </div>
        </v-card> -->

        <v-card flat class="border mb-4">
          <div class="d-flex justify-space-between">
            <v-card-title>Últimos usuários</v-card-title>
            <v-card-title>
              <v-btn @click="isDialogOpen = true" variant="tonal" size="small">Adicionar usuário</v-btn>
              
              <v-dialog 
                v-model="isDialogOpen"
                width="600px"
                >
                <v-card>
                  <v-card-title>Adicionar usuário</v-card-title>
                  <v-card-text>
                    <v-row>
                      <v-col>
                        <v-text-field label="Nome" variant="outlined"></v-text-field>
                      </v-col>

                      <v-col>
                        <v-text-field 
                          label="E-mail" 
                          variant="outlined"
                          :rules="emailRules"
                          ></v-text-field>
                      </v-col>
                    </v-row>

                   <v-select
                      label="Perfil"  
                      :items="['Admin', 'Gerente', 'Visitante']"
                      variant="outlined"
                    >
                    </v-select>
                  </v-card-text>

                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn variant="text" @click="isDialogOpen = false">Cancelar</v-btn>
                    <v-btn color="success" variant="tonal">Salvar</v-btn>
                  </v-card-actions>
                </v-card>
              </v-dialog>
            </v-card-title>
          </div>
        </v-card>
        

        <v-table
          fixed-header
          height="300px"
        >
        <thead>
          <tr>
            <th>Nome</th>
            <th>E-mail</th>
            <th>Perfil</th>
            <th>Ações</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Fulano</td>
            <td>fulano@gmail.com</td>
            <td>
              <v-chip color="success" variant="outlined" size="small">Admin</v-chip>
            </td>
            <td><v-btn icon="mdi-pencil" color="info" variant="tonal"></v-btn></td>
          </tr>
          <tr>
            <td>Ciclano</td>
            <td>ciclano@gmail.com</td>
            <td>
              <v-chip color="info" variant="outlined" size="small">Gerente</v-chip>
            </td>
            <td><v-btn icon="mdi-pencil" color="info" variant="tonal"></v-btn></td>
          </tr>
          <tr>
            <td>Beltrano</td>
            <td>beltrano@gmail.com</td>
            <td>
              <v-chip variant="outlined" size="small">Convidado</v-chip>
            </td>
            <td><v-btn icon="mdi-pencil" color="info" variant="tonal"></v-btn></td>
          </tr>
        </tbody>
        </v-table>

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
  const isDialogOpen = ref(false);

  const emailRules = [
    value => {
      if(value) {
        return true;
      }
      return 'O campo e-mail é obrigatório.';
    }, 
    value => {
      if(value.includes('@')) {
        return true;
      }
      return 'E-mail inválido.';
    }
  ];
</script>
