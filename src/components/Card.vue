<template>
  <div>
    {{ msg }}
    <b-col lg="3" sm="6" xs="12" v-for="car in cars" :key="car.marke">
      <b-card>
        <b-carousel
          id="carousel-1"
          v-model="slide"
          :interval="4000"
          controls
          indicators
        >
          <b-carousel-slide
            :img-src="foto"
            alt="car"
            class="d-block w-100"
            v-for="(foto, index) in car.nuotraukos"
            :key="index"
          >
          </b-carousel-slide>
        </b-carousel>
        <b-card-body>
          <b-card-text>{{ car.marke }}</b-card-text>
          <b-card-text>Modelis: {{ car.modelis }}</b-card-text>
          <b-card-text>Metai: {{ car.metai }}</b-card-text>
          <b-card-text class="highlighted"> {{ car.kaina }} € </b-card-text>
        </b-card-body>
      </b-card>
    </b-col>
    <b-button @click="addCar">Add Item</b-button>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    msg: String,
    cars: Array,
    addCar: Function
  }
};
</script>

<style scoped></style>
