<template>
  <div class="home">
    <profile-card/>
    <hello-world/>
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
   
  </div>
</template>

<script>
// @ is an alias to /src
import axios from "axios";
import HelloWorld from '../components/HelloWorld.vue';
import ProfileCard from '@/components/ProfileCard.vue';



export default {
  name: "Home",
  components: {
    HelloWorld,
    ProfileCard
   
  },
  data() {
    return {
      products:[],
      user:{}
    };
  },
  methods: {
    getProd() {
      var url = "http://localhost:3000/products";
      axios
        .get(url)
        .then((res) => {
          this.products = res.data.found;
          this.user = res.data.user;
        })
        .then(() => {
          // this.activestory = this.tales[0];
        });
    },
  },
  created(){
    this.getProd()
  }
};
</script>
