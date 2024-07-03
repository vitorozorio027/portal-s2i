<template>
  <v-app>
    <v-app-bar color="#1A237E" style="height: 55px;" class="d-flex justify-center align-center">
      <v-app-bar-title>
        <v-list class="d-flex bg-transparent">
          <v-list-item>
            <v-btn icon="mdi-menu" variant="text" @click="drawer = !drawer"></v-btn>
          </v-list-item>
          <v-list-item class="text-body-2 font-weight-black">{{ pageTitle }}</v-list-item>
        </v-list>
      </v-app-bar-title>
      <template #append>
        <div class="d-flex bg-transparent mr-6 align-center">
          <v-badge color="error" dot>
            <v-icon icon="mdi-bell" size="small"></v-icon>
          </v-badge>
          <v-icon icon="mdi-forum" size="small" class="mx-4"></v-icon>
          <v-avatar color="indigo-darken-4">
            <v-icon icon="mdi-account-circle"></v-icon>
          </v-avatar>
        </div>
      </template>
    </v-app-bar>
    
    <v-navigation-drawer
      :width="drawer ? '250' : '70'"
      class="pt-2 pb-2 px-2 h-100"
      v-model="drawer"
      :temporary="drawerstate"
      color="indigo-darken-4"
    >
      <v-list>
        <v-list-item class="mb-4" prepend-icon="mdi-home-account">
          <v-btn variant="text" text="Home" class="text-caption font-weight-regular" to="/Dashboard"></v-btn>
        </v-list-item>

        <div>
          <div class="d-flex align-center pl-4 mb-2">
            <div class="w-auto mr-4 font-weight-black" style="font-size: 12px;" v-if="drawer">Sistema</div>
            <div class="w-75"><hr></div>
          </div>

          <v-list-item prepend-icon="mdi-account-multiple-plus" class="text-caption">
            <v-btn variant="text" text="Usuarios" class="text-caption font-weight-regular" to="/usuarios"></v-btn>
          </v-list-item>

          <v-list-item prepend-icon="mdi-lan" class="text-caption">
            <v-btn variant="text" text="Cadastro de Sistema" class="text-caption font-weight-regular" to="/sistemas"></v-btn>
          </v-list-item>
        </div>

        <div>
          <div class="d-flex align-center pl-4 my-4">
            <div class="w-auto mr-4 font-weight-black" style="font-size: 12px;">Check-list de Inspeção</div>
            <div class="w-75"><hr></div>
          </div>

          <v-list-item v-for="[icon, text, too] in links" :key="icon" :prepend-icon="icon" class="text-caption">
            <v-btn variant="text" :text="text" class="text-caption font-weight-regular" :to="too"></v-btn>
          </v-list-item>
        </div>

        <div>
          <div class="d-flex align-center pl-4 mb-2 mt-4">
            <div class="w-auto mr-4 font-weight-black" style="font-size: 12px;">Relatório</div>
            <div class="w-75"><hr></div>
          </div>

          <v-list-item prepend-icon="mdi-database-settings" class="text-caption">
            <v-btn variant="text" class="text-caption font-weight-regular">Inspeção</v-btn>
          </v-list-item>

          <v-list-item prepend-icon="mdi-list-status" class="text-caption">
            <v-btn variant="text" class="text-caption font-weight-regular">Acompanhamento</v-btn>
          </v-list-item>
        </div>
      </v-list>
      
      <!-- Botão de Logout -->
      <v-btn @click="confirmLogout" icon="mdi-logout" style="float: right; margin-top: 70px; background-color: #1A237E; color: white"></v-btn>
    </v-navigation-drawer>

    <!-- Popup de confirmação -->
    <v-dialog v-model="dialog" max-width="300">
      <v-card>
        <v-card-title class="headline">Confirmar Saída</v-card-title>
        <v-card-text>
          Tem certeza que deseja sair?
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="blue darken-1" text @click="dialog = false">Cancelar</v-btn>
          <v-btn color="blue darken-1" text @click="logout">Sim</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>

    <slot />
  </v-app>
</template>

<script setup>
import { ref } from 'vue'

const pageTitle = ref('Página Principal')
const drawer = ref(false)
const drawerstate = ref(true) // Adicionei um valor para drawerstate, substitua pelo seu estado real se necessário
const dialog = ref(false)

const links = [
  ['mdi-book-edit', 'Programação Rota', '/programacao']
]

function confirmLogout() {
  dialog.value = true
}

function logout() {
  // Aqui você pode adicionar a lógica para logout, como redirecionar o usuário
  // para a página de login ou a página inicial
  console.log('Logout confirmed')
  // Simulando redirecionamento para a página inicial
  window.location.href = '/'
}
</script>
