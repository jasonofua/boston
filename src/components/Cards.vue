<template>
  <div class="container-fluid">
    <div class="row">
      <div
        class="col-lg-3 col-md-4 col-sm-12 col-12"
        v-for="(card, index) in cards"
        v-bind:key="index"
      >
        <div class="card col-12 p-0 my-1">
          <div class="col-12 p-0 card-img-container">
            <img :src="card" class="card-img-top" alt="..." />
          </div>
          <div class="card-body">
            <a href="#" class="btn btn-primary mx-auto">View More</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import axios from "axios";
import VueAxios from "vue-axios";
Vue.use(VueAxios, axios);
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "card",
  data() {
    return { cards: undefined };
  },
  mounted() {
    Vue.axios
      .get(`https://boston-dynamics-cxhyclwxeq-uc.a.run.app/getAllFiles`)
      .then((res) => {
        console.log(res.data.data[0]);
        this.cards = res.data.data;
      });
  },
};
</script>

<style lang="scss">
.card-img-container {
  height: 200px;
}
.card-img-top {
  width: 100%;
}
</style>
