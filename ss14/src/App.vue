<template>
  <div>
    <v-container class="mt-12">
      <v-row>
        <v-col cols="12" md="8">
          <v-card outlined class="pa-4 shadow-lg">
            <v-card-title class="text-h5 font-weight-bold"
              >Item Cart</v-card-title
            >
            <v-card-subtitle>Product Summary</v-card-subtitle>

            <v-list-item three-line class="px-0">
              <v-list-item-avatar tile size="100" class="rounded-lg">
                <v-img
                  src="https://img.freepik.com/free-vector/gradient-particle-wave-background_23-2150517309.jpg"
                  alt="Product Image"
                ></v-img>
              </v-list-item-avatar>
              <v-list-item-content>
                <v-list-item-title class="text-h6 mb-1"
                  >Cute Soft Teddybear</v-list-item-title
                >
                <v-list-item-subtitle
                  >Size: 8 | Color: Dark Red</v-list-item-subtitle
                >
                <v-list-item-subtitle class="mt-2">
                  <v-btn icon small @click="decreaseQuantity">
                    <v-icon>mdi-minus</v-icon>
                  </v-btn>
                  <span class="mx-2">{{ quantity }}</span>
                  <v-btn icon small @click="increaseQuantity">
                    <v-icon>mdi-plus</v-icon>
                  </v-btn>
                </v-list-item-subtitle>
              </v-list-item-content>
              <v-list-item-action class="align-self-center">
                <v-list-item-title class="text-h6"
                  >${{ totalPrice }}</v-list-item-title
                >
                <v-btn icon color="red" class="mt-2">
                  <v-icon>mdi-delete</v-icon>
                </v-btn>
              </v-list-item-action>
            </v-list-item>
          </v-card>

          <v-row class="mt-6">
            <v-col cols="6">
              <v-btn color="primary" block outlined>Continue Shopping</v-btn>
            </v-col>
            <v-col cols="6">
              <v-btn color="secondary" block>Checkout</v-btn>
            </v-col>
          </v-row>
        </v-col>

        <v-col cols="12" md="4">
          <v-card outlined class="pa-4 shadow-lg">
            <v-card-title class="text-h5 font-weight-bold"
              >Order Summary</v-card-title
            >
            <v-list-item dense>
              <v-list-item-content>Sub Total</v-list-item-content>
              <v-list-item-content class="align-end"
                >${{ subTotal }}</v-list-item-content
              >
            </v-list-item>
            <v-list-item dense>
              <v-list-item-content>Discount (5%)</v-list-item-content>
              <v-list-item-content class="align-end red--text"
                >- ${{ discount }}</v-list-item-content
              >
            </v-list-item>
            <v-list-item dense>
              <v-list-item-content>Shipping Charges</v-list-item-content>
              <v-list-item-content class="align-end">-</v-list-item-content>
            </v-list-item>
            <v-divider class="my-2"></v-divider>
            <v-list-item>
              <v-list-item-content>
                <span class="font-weight-bold">Total</span>
              </v-list-item-content>
              <v-list-item-content class="align-end">
                <span class="font-weight-bold">${{ total }}</span>
              </v-list-item-content>
            </v-list-item>
          </v-card>
        </v-col>
      </v-row>
    </v-container>

    <v-container>
      <v-row>
        <v-col cols="12" md="6">
          <v-carousel hide-delimiter-background>
            <v-carousel-item
              v-for="(image, index) in images"
              :key="index"
              :src="image"
            >
              <v-img
                :src="image"
                alt="Product Image"
                class="rounded-lg shadow-lg"
                height="400"
                width="100%"
                contain
              ></v-img>
            </v-carousel-item>
          </v-carousel>

          <v-row class="mt-2">
            <v-col v-for="(thumb, index) in images" :key="index" cols="2">
              <v-img
                :src="thumb"
                :alt="`Thumbnail ${index + 1}`"
                class="rounded-lg shadow"
                height="80"
                width="100%"
                contain
                @click="selectImage(index)"
              ></v-img>
            </v-col>
          </v-row>
        </v-col>

        <v-col cols="12" md="6">
          <v-chip color="success" label class="mb-2">In Stock</v-chip>
          <v-chip color="info" label class="mb-2 ml-2">Kids</v-chip>
          <h1 class="text-h4 font-weight-bold mb-2">Cute Soft Teddybear</h1>
          <p class="text-h5 font-weight-bold">$200</p>
          <div class="d-flex align-center">
            <v-rating
              v-model="rating"
              color="amber"
              dense
              half-increments
              readonly
              size="18"
            ></v-rating>
            <span class="grey--text ml-2">({{ reviews }} reviews)</span>
          </div>

          <v-row class="mt-6">
            <v-col cols="12">
              <span class="font-weight-medium mr-4">Colors:</span>
              <v-btn
                v-for="color in colors"
                :key="color"
                :color="color"
                fab
                small
                class="mr-2 rounded-circle w-1 h-1"
              ></v-btn>
            </v-col>
          </v-row>

          <v-row class="mt-6">
            <v-col cols="12" class="d-flex align-center">
              <span class="font-weight-medium mr-4">Quantity:</span>
              <v-btn icon @click="decreaseQuantity">
                <v-icon>mdi-minus</v-icon>
              </v-btn>
              <span class="mx-4 text-h6">{{ quantity }}</span>
              <v-btn icon @click="increaseQuantity">
                <v-icon>mdi-plus</v-icon>
              </v-btn>
            </v-col>
          </v-row>

          <v-row class="mt-6">
            <v-col cols="6">
              <v-btn color="primary" x-large block>Buy Now</v-btn>
            </v-col>
            <v-col cols="6">
              <v-btn color="secondary" x-large block outlined
                >Add To Cart</v-btn
              >
            </v-col>
          </v-row>

          <v-row class="mt-4">
            <v-col cols="12">
              <p class="text-body-2">Dispatched in 2-3 weeks</p>
              <a href="#" class="text-body-2 primary--text"
                >Why the longer time for delivery?</a
              >
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script setup>
import { ref } from "vue";
const quantity = ref(1);
const rating = ref(4.5);
const reviews = ref(236);
const colors = ref(["#FF9800", "#4CAF50", "#2196F3", "#9C27B0"]);
const price = ref(200);
const images = ref([
  "https://img.freepik.com/free-vector/gradient-particle-wave-background_23-2150517309.jpg",
  "https://png.pngtree.com/thumb_back/fh260/background/20230408/pngtree-rainbow-curves-abstract-colorful-background-image_2164067.jpg",
  "https://images.pexels.com/photos/531880/pexels-photo-531880.jpeg?cs=srgb&dl=pexels-pixabay-531880.jpg&fm=jpg",
  "https://static.vecteezy.com/system/resources/thumbnails/023/669/545/small/abstract-gradient-pink-blue-liquid-wave-background-free-vector.jpg",
  "https://wallpaperaccess.com/full/637969.jpg",
]);

const selectImage = (index) => {
  carousel.value.goToSlide(index);
};

const increaseQuantity = () => {
  quantity.value++;
};

const decreaseQuantity = () => {
  if (quantity.value > 1) {
    quantity.value--;
  }
};
</script>

<style scoped>
.shadow-lg {
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}
</style>
