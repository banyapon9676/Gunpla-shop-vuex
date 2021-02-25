<template>
  <div class="home">
    <b-card-group deck>
      <b-card bg-variant="light" header="Total product price" class="text-center">
        <b-card-text><h3>{{ cSum }} ฿</h3></b-card-text>
       <b-button variant="danger" @click="delet">Clear product</b-button>
      </b-card>
    </b-card-group>
    <b-container>
      <br />
      <b-row>
        <b-col cols="lg-4" v-for="index in cList" :key="index">
          <Product
            :img="index.img"
            :price="index.price"
            :nameProduct="index.nameProduct"
            @update-cart="UpProduct"
          />
        </b-col>
      </b-row>
    </b-container>
    <b-modal id="bv-modal-example" hide-footer>
      <div class="d-block text-center">
        <p>ใส่ตะกร้าเรียบร้อย</p>
      </div>
      <b-button class="mt-3" block @click="$bvModal.hide('bv-modal-example')"
        >ปิด</b-button
      >
    </b-modal>
  </div>
</template>

<script>
import { mapGetters,mapMutations } from "vuex";
import Product from "@/components/product.vue";
export default {
  name: "Home",
  components: {
    Product,
  },
  methods: {
   ...mapMutations(["delet"]),
  },
  computed: {
    ...mapGetters(["cList", "UpProduct", "cSum"]),
  },
  data() {
    return {
      fields: ["nameProduct", "price", "num", "Sum"],
    };
  }
};
</script>