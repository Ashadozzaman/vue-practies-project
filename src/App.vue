<template>
  <div>
    <h1>{{ msg }}</h1>
    <ProductCard v-for="product in products" :key="product.title" :product="product" @buy-now-clicked="buyClicked"
      @buy-add-to-cart-clicked="addToCartClicked" @toogle-clicked-like="toogleClickedLike"></ProductCard>
    <!-- <TheCard cardTitle="About Me ">
      <template v-slot:default>
        <p>Hi I am Ashadozzaman Shvou</p>
      </template>
      <template v-slot:footer>
        <a href="http://">Learn More</a>
      </template>
    </TheCard>
    <TheCard cardTitle="Apple iPhone 14 Pro">
      <template v-slot:default>
        <img
          src="https://adminapi.applegadgetsbd.com/storage/media/large/iPhone-14-Pro-Max-9907.jpg"
          alt=""
        />
      </template>

      <template v-slot:footer>
        <button>Buy Now</button>
        <button>Add Cart</button>
      </template>
    </TheCard>
    <TheCard cardTitle="Service">
      <u>
        <li>Html</li>
        <li>Slot</li>
        <li>Props</li>
      </u>
    </TheCard> -->
    <!-- <FirstComponentVue 
            v-for="contact in contacts"
            :key="contact.name"
            :name="contact.name" 
            :website-address="contact.websiteAddress" 
            :phone="contact.phone">
        </FirstComponentVue> -->
  </div>
</template>

<script>
// import FirstComponentVue from './FirstComponent.vue';
//import TheCard from "./TheCard.vue";
// import ProductCard from "./ProductCard.vue";
import TheRatting from './TheRatting.vue';

export default {
  data() {
    return {
      msg: "Vue V-Model",
      contacts: [{
        name: "Ashadozzaman",
        phone: "017111111",
        websiteAddress: "ashadozzaman.com",
      },
      {
        name: "Shvou",
        phone: "018111111",
        websiteAddress: "shvoua.com",
      },
      {
        name: "Karim",
        phone: "019111111",
      },
      ],
      products: [{
        title: "Apple 14 pro MAX",
        thumbnail: "https://adminapi.applegadgetsbd.com/storage/media/large/iPhone-14-Pro-Max-9907.jpg",
        price: "$19345",
        like: true
      },
      {
        title: "Samsung A20",
        thumbnail: "https://www.mobilebd.co/wp-content/uploads/2020/08/Samsung-Galaxy-A20-Official-image.jpg",
        price: "$11345",
        like: false
      },
      {
        title: "MI Phone",
        thumbnail: "https://fdn2.gsmarena.com/vv/bigpic/xiaomi-mi-a2-lite.jpg",
        price: "$1934",
        like: true
      },
      ],
    };
  },
  methods: {
    buyClicked() {
      console.log("Buying....");
    },
    addToCartClicked(product) {
      console.log("Add to cart...", product);
    },
    toogleClickedLike(product) {
      product.like = !product.like
    }
  },
  components: {
    // FirstComponentVue,
    //TheCard,
    ProductCard,
  },
};
</script>
