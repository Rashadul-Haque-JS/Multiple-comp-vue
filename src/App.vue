<template>
  <div id="app">
    <!-- <Cookie/> -->
    <div>
      <div class="top-part">
        <Header />
        <Toast :hide='message'/>
        </div>
      

      <Navigation />
    </div>
    <div class="main-part">
      <Main v-bind:productsArray="products" />
      <div class="aside-part">
        <LoginForm/>
        <Aside v-bind:toggle="toggleArray" />
        <Preloader />
        
        <ProductsCard v-bind:product="products[2]" />
      </div>
    </div>
    <div class="persons">
      <PersonCard :keys='object'/>
    </div>
    
    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Navigation from "./components/Navigation.vue";
import Main from "./components/Main.vue";
import Aside from "./components/Aside.vue";
import Footer from "./components/Footer.vue";
import ProductsCard from "./components/ProductsCard.vue";
import Preloader from "./components/Preloader.vue";
import Toast from './components/Toast.vue';
// import Cookie from './components/Cookie.vue'
import PersonCard from './components/PersonsCard.vue'
import LoginForm from './components/LoginForm.vue'

export default {
  components: {
    Header,
    Navigation,
    Main,
    Aside,
    Footer,
    ProductsCard,
    Preloader,
    Toast,
    // Cookie,
    PersonCard,
    LoginForm
  },
  data() {
    return {
      toggleArray: ["Toggle One", "Toggle Two", "Toggle Three"],
      message: "Your shopping is good for our money bag! 👌",
      object: null,

    
      products: [
        {
          productId: 1000,
          productName: "delightful chocolate Ilise",
          productImage: "https://picsum.photos/400?image=659",
          productStock: 81,
          productPrice: "23488.67",
          productSalePrice: "23488.67",
          rating: 4,
        },
        {
          productId: 1009,
          productName: "indirect indigo Fiona",
          productImage: "https://picsum.photos/400?image=583",
          productStock: 49,
          productPrice: "40702.21",
          productSalePrice: "4477.24",
          rating: 1,
        },
        {
          productId: 1035,
          productName: "complicated m Esmaria",
          productImage: "https://picsum.photos/400?image=648",
          productStock: 69,
          productPrice: "3128.23",
          productSalePrice: "938.47",
          rating: 4,
        },
        {
          productId: 1046,
          productName: "voiceless emerald Sarita",
          productImage: "https://picsum.photos/400?image=695",
          productStock: 48,
          productPrice: "21625.98",
          productSalePrice: "8001.61",
          rating: 3,
        },
        {
          productId: 1047,
          productName: "old lime Elvera",
          productImage: "https://picsum.photos/400?image=622",
          productStock: 4,
          productPrice: "30869.36",
          productSalePrice: "30869.36",
          rating: 5,
        },
        {
          productId: 1051,
          productName: "unfortunate tan Maris",
          productImage: "https://picsum.photos/400?image=648",
          productStock: 63,
          productPrice: "39042.14",
          productSalePrice: "11322.22",
          rating: 2,
        },
        {
          productId: 1063,
          productName: "lovely brown Theressa",
          productImage: "https://picsum.photos/400?image=891",
          productStock: 31,
          productPrice: "40426.73",
          productSalePrice: "12936.55",
          rating: 4,
        },
        {
          productId: 1068,
          productName: "primary gold Tera",
          productImage: "https://picsum.photos/400?image=583",
          productStock: 88,
          productPrice: "25121.63",
          productSalePrice: "25121.63",
          rating: 4,
        },
        {
          productId: 1000,
          productName: "delightful chocolate Ilise",
          productImage: "https://picsum.photos/400?image=659",
          productStock: 81,
          productPrice: "23488.67",
          productSalePrice: "23488.67",
          rating: 4,
        },
        {
          productId: 1009,
          productName: "indirect indigo Fiona",
          productImage: "https://picsum.photos/400?image=583",
          productStock: 49,
          productPrice: "40702.21",
          productSalePrice: "4477.24",
          rating: 1,
        },
        {
          productId: 1035,
          productName: "complicated m Esmaria",
          productImage: "https://picsum.photos/400?image=648",
          productStock: 69,
          productPrice: "3128.23",
          productSalePrice: "938.47",
          rating: 4,
        },
        {
          productId: 1046,
          productName: "voiceless emerald Sarita",
          productImage: "https://picsum.photos/400?image=695",
          productStock: 48,
          productPrice: "21625.98",
          productSalePrice: "8001.61",
          rating: 3,
        },
      ],
     
    };
  },
 async created() {
		try {
			const response = await fetch("https://randomuser.me/api/?results=12");
			const data = await response.json();
			this.object = data;
	
		} catch (error) {
			console.error(error);
		}
	},
};
</script>

<style >
* {
  margin: 0px;
  box-sizing: border-box;
  padding: 0px;
}
body {
  margin-bottom: 50px;
  margin: 0px 20px;
  background-color: #d7d8c9;
}
#app {
  display: grid;
  grid-template-columns: 1fr;

}
.top-part{
  display: grid;
  grid-template-columns: 2fr 1fr;
  background-color: #fcde67;
}

.top-part div:nth-of-type(2){
  margin-right: 30px;
  margin-top: 10px;
}
.main-part {
  display: grid;
  grid-template-columns: 4fr 1fr;
}
.aside-part {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  background-color: #248ea6;
  
}
.persons{
  min-height: 1467px;
  background-color:#5bccf6;
  position: relative;
}

</style>