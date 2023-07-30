<script>
export default {
  name: "ProductDisplay",
  data() {
    return {
      loading: false,
      noIndex: 0,
      rightCategory: false,
      product: {},
    };
  },
  methods: {
    async panggilAPI() {
      const response = await fetch(
        `https://fakestoreapi.com/products/${this.noIndex}`
      );
      const result = await response.json;
      return result;
    },
    async getProduct() {
      this.loading = true;

      if ((this.noIndex = 20)) {
        this.noIndex = 1;
      } else {
        this.noIndex++;
      }

      let data = await this.panggilAPI();
      if (
        data.category == "men's clothing" ||
        data.category == "women's clothing"
      ) {
        this.product = { data };
        this.rightCategory = true;
      } else {
        this.rightCategory = false;
      }

      this.loading = false;
    },
    mounted() {
      this.getProduct();
    },
  },
};
</script>

<template>
  <div class="container">
    <!-- Loading Skeleton -->
    <div v-if="loading" class="product_container">
      <!-- Left Side -->
      <div class="skeleton_product_img"></div>

      <!-- Right Side -->
      <div>
        <div class="skeleton_title_product"></div>
        <div>
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

    <!-- Display Produk -->
    <div class="product_container">
      <div class="left_side">
        <img class="product_img" src="../assets/img/baju.png" alt="" />
      </div>
      <div class="right_side">
        <h1 class="title_product">
          Lock and Love Women's Removable Hooded Faux Leather Moto Biker Jacket
        </h1>
        <div class="product_categorys">
          <span class="product_category">womens's clothing</span>
        </div>
        <p class="product_desc">
          100% POLYURETHANE(shell) 100% POLYESTER(lining) 75% POLYESTER 25%
          COTTON (SWEATER), Faux leather material for style and comfort / 2
          pockets of front, 2-For-One Hooded denim style faux leather jacket,
          Button detail on waist / Detail stitching at sides, HAND WASH ONLY /
          DO NOT BLEACH / LINE DRY / DO NOT IRON
        </p>
        <h3 class="price_product">$30</h3>
        <div class="button_area">
          <button class="btn btn_primary">Buy Now</button>
          <button class="btn btn_secondary">Next Product</button>
        </div>
      </div>
    </div>
  </div>
</template>
