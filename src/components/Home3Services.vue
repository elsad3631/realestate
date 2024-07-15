<template>
  <div class="row align-items-center">
    <div
      class="col-xl-4 col-md-6 m-lg-b30 aos-item aos-init aos-animate"
      v-for="({ id, icon, title, description }, ind) in servicesCard"
      :key="ind"
    >
      <div class="icon-bx-wraper style-9">
        <div class="icon-lg">
          <span class="icon-cell">
            <i :class="icon"></i>
          </span>
        </div>
        <div class="icon-content">
          <h4 class="dz-title">{{ title }}</h4>
          <p>{{ description }}</p>
          <RouterLink :to="{ name: 'services_details', params: { id: id }}" class="btn btn-primary btn-rounded btn-sm hover-icon">
            <span>Dettaglio</span>
            <i class="fas fa-arrow-right"></i>
          </RouterLink>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  setup() {
    return {
      servicesCard: [
        { id: 1, icon: 'flaticon-blueprint-1', title: 'PRATICHE EDILIZIE', description: 'Devi ristrutturare un ufficio, un appartamento, un negozio? Le normative cambiano con grande rapidità: è quindi importane rivolgersi a tecnici qualificati e costantemente aggiornati per essere guidati con competenza. Ogni immobile ha la sua storia, le sue peculiarità: col nostro studio non dovrai preoccuparti dei permessi e di tutta la documentazione da presentare.' },
        { id: 2, icon: 'flaticon-crane', title: 'PRATICHE CATASTALI', description: 'Rilievo del fabbricato, realizzazione dei modelli per l’attribuzione della rendita catastale, redazione delle planimetrie: il nostro studio si occupa di tutte le pratiche catastali e di edilizia, per privati e per imprese.  E se il vostro immobile ha subito una variazione? Ci occupiamo anche di pratiche di accatastamento a seguito di frazionamenti o ristrutturazioni.' },
        { id: 3, icon: 'flaticon-interior-design-1', title: 'PERIZIE, STIME E TRIBUNALE', description: 'Devi comprare o vendere un immobile? Dividere il patrimonio immobiliare? I nostri professionisti hanno una lunga esperienza nel campo delle stime. Aiutiamo i nostri clienti nella compravendita, nella divisione, ma anche nella redazione di perizie di stima giurate e stime in campo contenzioso. Davanti al giudice possiamo essere i tuoi Consulenti Tecnici di Parte e di Ufficio, il tuo perito di fiducia.' },
        // { icon: 'flaticon-home', title: 'Architecture & build.' }
      ]
    }
  }
})
</script>

<style scoped></style>
