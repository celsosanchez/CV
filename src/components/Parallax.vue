<template>
  <div>
    <v-row>
      <parallax-container class="box1">
        <v-img
          max-height="100vh"
          max-width="100vw"
          src="https://images.unsplash.com/photo-1545987796-200677ee1011?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1950&q=80"
        ></v-img>

        <parallax-element
          :parallaxStrength="-5"
          :type="'depth'"
          class="box overlay"
        >
          <div class="d-flex flex-row">
            <v-col>
              <v-img
                contain
                max-height="97.5vh"
                max-width="50vw"
                src="@/assets/photo.png"
              ></v-img>
            </v-col>
            <v-col>
              <v-card>
                <v-card-title
                  ><h2>>{{ greetings }}</h2></v-card-title
                >
              </v-card>
            </v-col>
          </div>
        </parallax-element>
      </parallax-container>
    </v-row>
    <v-row>
      <parallax-container class="box1">
        <v-img
          max-height="100vh"
          max-width="100vw"
          src="https://images.unsplash.com/photo-1499951360447-b19be8fe80f5?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1950&q=80"
        ></v-img>
        <parallax-element
          :parallaxStrength="-10"
          :type="'depth'"
          class="box overlay"
        >
          <v-img
            max-height="868"
            max-width="824"
            src="https://dev.w3.org/SVG/tools/svgweb/samples/svg-files/gallardo.svg"
          ></v-img>
        </parallax-element>
      </parallax-container>
    </v-row>
  </div>
</template>
<script>
import parallaxContainer from "@/components/parallax-container.vue";
import parallaxElement from "@/components/parallax-element.vue";
export default {
  components: {
    parallaxElement,
    parallaxContainer,
  },
  data() {
    return {
      greetings: "#^@?%&*",
      textList: ["HelloWorld!","#^@?%&*", "BonjourMonde!","?%&*#&","HolaMundo!","&*#&$^"],
      counter: 0,
    };
  },
  methods: {},
  created() {
    setInterval(() => {
        if (this.counter == 6) this.counter = 0

      this.greetings = this.textList[this.counter];
      this.counter += 1;
    }, 1000);
  },

  mounted() {},
};
</script>
<style scoped>
/* .box {
  width: 100%;
  height: 100%;
  position: static;
  top: 0;
  left: 0;
} */
.box1 {
  width: 100%;
  height: 100%;
  position: static;
  top: 0;
  left: 0;
}
.overlay {
  z-index: 3;
  top: 0;
  left: 0vw;
  top: 10vh;
  position: absolute;
}
</style>
