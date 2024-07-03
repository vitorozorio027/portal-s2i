<template>
  <v-row class="info-cards">
    <v-col cols="4">
      <v-card class="info-card" height="150" elevation="6" color="indigo-darken-4">
        <v-card-item class="h-100">
          <div class="d-flex h-100 align-center">
            <div class="w-50 d-flex flex-column justify-center pa-2">
              <p class="text-caption">Qtde. Locais Cadastrados</p>
              <p class="text-h3 mt-4">0</p>
            </div>
            <div class="w-50 text-end"><v-icon class="text-h2" icon="mdi-database-cog-outline"></v-icon></div>
          </div>
        </v-card-item>
      </v-card>
    </v-col>

    <v-col cols="4">
      <v-card class="info-card" height="150" elevation="6" color="indigo-darken-4">
        <v-card-item class="h-100">
          <div class="d-flex h-100 align-center">
            <div class="w-50 d-flex flex-column justify-center pa-2">
              <p class="text-caption">Qtde. Locais Programados</p>
              <p class="text-h3 mt-4">0</p>
            </div>
            <div class="w-50 text-end"><v-icon class="text-h2" icon="mdi-timer-sand"></v-icon></div>
          </div>
        </v-card-item>
      </v-card>
    </v-col>

    <v-col cols="4">
      <v-card class="info-card" height="150" elevation="6" color="indigo-darken-4">
        <v-card-item class="h-100">
          <div class="d-flex h-100 align-center">
            <div class="w-50 d-flex flex-column justify-center pa-2">
              <p class="text-caption">Qtde. Locais Concluídos</p>
              <p class="text-h3 mt-4">0</p>
            </div>
            <div class="w-50 text-end"><v-icon class="text-h2" icon="mdi-check-circle"></v-icon></div>
          </div>
        </v-card-item>
      </v-card>
    </v-col>

    <v-col cols="4">
      <v-card class="info-card" height="150" elevation="6" color="indigo-darken-4">
        <v-card-item class="h-100">
          <div class="d-flex h-100 align-center">
            <div class="w-50 d-flex flex-column justify-center pa-2">
              <p class="text-caption">Total Anomalia Detectada</p>
              <p class="text-h3 mt-4">0</p>
            </div>
            <div class="w-50 text-end"><v-icon class="text-h2" icon="mdi-flash-alert-outline"></v-icon></div>
          </div>
        </v-card-item>
      </v-card>
    </v-col>

    <v-col cols="4">
      <v-card class="info-card" height="150" elevation="6" color="indigo-darken-4">
        <v-card-item class="h-100">
          <div class="d-flex h-100 align-center">
            <div class="w-50 d-flex flex-column justify-center pa-2">
              <p class="text-caption">Total Anomalia Pendente</p>
              <p class="text-h3 mt-4">0</p>
            </div>
            <div class="w-50 text-end"><v-icon class="text-h2" icon="mdi-alert-remove"></v-icon></div>
          </div>
        </v-card-item>
      </v-card>
    </v-col>

    <v-col cols="4">
      <v-card class="info-card" height="150" elevation="6" color="indigo-darken-4">
        <v-card-item class="h-100">
          <div class="d-flex h-100 align-center">
            <div class="w-50 d-flex flex-column justify-center pa-2">
              <p class="text-caption">Total Anomalia Concluída</p>
              <p class="text-h3 mt-4">0</p>
            </div>
            <div class="w-50 text-end"><v-icon class="text-h2" icon="mdi-check-all"></v-icon></div>
          </div>
        </v-card-item>
      </v-card>
    </v-col>
  </v-row>
</template>

<script setup>
// Lógica de dados ou importações necessárias
</script>

<style scoped>
.info-cards {
  margin-bottom: 20px;
}

.info-card {
  transition: all 0.3s ease;
  border-radius: 12px;
}

.info-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
}

.text-caption {
  color: #ffffff;
  font-size: 14px;
  margin-bottom: 8px;
}

.text-h3 {
  color: #ffffff;
  font-size: 24px;
  font-weight: bold;
}

.text-h2 {
  color: #ffffff;
}
</style>
