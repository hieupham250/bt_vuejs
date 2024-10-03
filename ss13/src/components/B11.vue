<template>
  <div class="product-page">
    <div class="sidebar">
      <h4>Filters</h4>

      <div class="filter-section">
        <h5>Categories</h5>
        <v-checkbox
          v-model="selectedCategories"
          label="All"
          value="all"
        ></v-checkbox>
        <v-checkbox
          v-model="selectedCategories"
          label="Kitchen"
          value="kitchen"
        ></v-checkbox>
        <v-checkbox
          v-model="selectedCategories"
          label="Electronics"
          value="electronics"
        ></v-checkbox>
      </div>

      <div class="filter-section">
        <h5>Colors</h5>
        <v-select
          v-model="selectedColors"
          :items="colors"
          label="Select Colors"
          multiple
          chips
        ></v-select>
      </div>

      <div class="filter-section">
        <h5>Price</h5>
        <v-range-slider
          v-model="priceRange"
          :max="200"
          :min="0"
          :step="10"
          thumb-label="always"
        ></v-range-slider>
      </div>

      <div class="filter-section">
        <h5>Rating</h5>
        <v-rating
          v-model="minRating"
          color="yellow-darken-3"
          half-increments
        ></v-rating>
      </div>
    </div>

    <div class="main-content">
      <div class="search-bar">
        <h4>Products</h4>
        <v-text-field
          v-model="searchQuery"
          prepend-inner-icon="mdi-magnify"
          label="Search products..."
          single-line
          hide-details
        ></v-text-field>
      </div>

      <v-card>
        <v-tabs v-model="tab" align-tabs="center" color="deep-purple-accent-4">
          <v-tab :value="1">Landscape</v-tab>
          <v-tab :value="2">City</v-tab>
          <v-tab :value="3">Abstract</v-tab>
        </v-tabs>

        <v-window v-model="tab">
          <v-window-item v-for="n in 3" :key="n" :value="n">
            <v-container fluid>
              <v-row>
                <v-col v-for="i in 6" :key="i" cols="12" sm="6" md="4">
                  <v-card>
                    <v-img
                      :src="`https://picsum.photos/500/300?image=${
                        i * n * 5 + 10
                      }`"
                      height="200"
                      cover
                    ></v-img>
                    <v-card-title>Product {{ i * n }}</v-card-title>
                    <v-card-subtitle
                      >${{ (i * n * 15).toFixed(2) }}</v-card-subtitle
                    >
                    <v-card-text>
                      <v-rating
                        :model-value="((i * n) % 5) + 1"
                        color="amber"
                        density="compact"
                        half-incrementsreadonly
                        size="small"
                      ></v-rating>
                    </v-card-text>
                  </v-card>
                </v-col>
              </v-row>
            </v-container>
          </v-window-item>
        </v-window>
      </v-card>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    tab: 1,
    searchQuery: "",
    selectedCategories: ["all"],
    selectedColors: [],
    colors: ["Red", "Blue", "Green", "Yellow", "Purple"],
    priceRange: [0, 200],
    minRating: 3,
  }),
};
</script>

<style scoped>
.product-page {
  display: flex;
  gap: 20px;
}

.sidebar {
  width: 250px;
  padding: 20px;
  background-color: #f5f5f5;
  border-radius: 8px;
}

.main-content {
  flex-grow: 1;
}

.filter-section {
  margin-bottom: 20px;
}

h4,
h5 {
  margin-bottom: 10px;
}

.search-bar {
  margin-bottom: 20px;
}

.v-card {
  padding: 20px;
}
</style>
