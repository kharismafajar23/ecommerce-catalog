<template>
  <div>
    <!-- Loading Skeleton -->
    <div v-if="isLoading" class="product_container">
      <!-- Left Side -->
      <div class="skeleton_product_img"></div>

      <!-- Right Side -->
      <div>
        <div class="skeleton_title_product"></div>
        <div class="flex space_between">
          <div class="skeleton_category_product"></div>
          <div class="skeleton_rating_product"></div>
        </div>
        <div class="skeleton_desc_product"></div>
        <div class="skeleton_price_product"></div>
        <div class="button_area">
          <div class="skeleton_button"></div>
          <div class="skeleton_button"></div>
        </div>
      </div>
    </div>
    <!-- End Skeleton -->

    <!-- HTML Utama -->
    <div v-else class="product_container">
      <!-- left side -->
      <div class="left_side">
        <img src="../assets/img/baju.png" alt="" />
      </div>
      <!-- right side -->
      <div class="right_side">
        <h1 class="title_product">Ini judul ya</h1>
        <div class="product_categorys">
          <p>Kategori Poduk</p>
        </div>
        <p class="product_desc">Ini deskripsi product ya ges ya</p>
        <h3 class="price_product">Harga disini</h3>
        <div class="button_area">
          <button class="btn btn_primary">Buy Now</button>
          <button class="btn btn_secondary">Next Product</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductDisplay",
  data() {
    return {
      isLoading: false,
      noIndex: 0,
      rightCategory: false,
      product: {},
    };
  },
  // methods: {
  //   //Panggil API
  //   async panggilAPI() {
  //     const response = await fetch(
  //       `https://fakestoreapi.com/products/${this.noIndex}`
  //     );
  //     const result = await response.json();
  //     return result;
  //   },

  //   // Fungsi get product
  //   async getProduct() {
  //     this.isLoading = true;

  //     // jika no index 20 maka kembali ke 1
  //     if (this.noIndex == 20) {
  //       this.noIndex = 1;

  //       // selain itu index bertambah 1
  //     } else {
  //       this.noIndex++;
  //     }

  //     let data = await this.panggilAPI();
  //     // jika kategori = mens / women
  //     if (
  //       data.category == "men's clothing" ||
  //       data.category == "womens's clothing"
  //     ) {
  //       // masukkan ke product
  //       this.product = { data };
  //       this.rightCategory = true;

  //       // jika category selain men's/women's
  //       this.rightCategory = false;
  //     }

  //     this.isLoading = false;
  //   },
  // },
  mounted() {
    this.getProduct();
  },
};
</script>
