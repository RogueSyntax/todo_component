<template>
  <v-container class="inputBox">
    <div>
      <Head title="เพิ่มงาน/การบ้าน"/>
      <Form @rtb="pushWork" />
    </div>
    <v-container>
      <h1>งาน/การบ้าน ทั้งหมด</h1>

      <v-list shaped>
        <v-list-item-group v-model="selectedItem" color="green">
          <v-list-item v-for="(item, i) in additems" :key="i">
            <v-list-item-content>
              <v-list-item-title
                v-text="item.text"
                id="table"
              ></v-list-item-title>
            </v-list-item-content>

            <v-btn
              class="mx-2"
              fab
              dark
              small
              color="error"
              id="del"
              @click="del(i)"
            >
              <v-icon dark> mdi-minus </v-icon>
            </v-btn>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-container>
  </v-container>
</template>

<script src="//cdn.jsdelivr.net/npm/sweetalert2@11"></script>

<script>
import Form from "../components/form.vue";
import Head from "../components/head.vue";

export default {
  components: {
    Form,Head,
  },

  data() {
    return {
      selectedItem: 1,
      additems: [],
    };
  },

  methods: {
    pushWork(i) {
      this.additems.push(i);
    },
    del(index) {
      this.additems.splice(index, 1);
    },
  },
};
</script>

<style>
#head {
  display: flex;
  justify-content: center;
}

h2 {
  margin: 20px;
  display: flex;
  justify-content: center;
  font-size: 25px;
}

h1 {
  font-size: 20px;
  display: flex;
  justify-content: center;
}

#del {
  margin: 5px;
}
#table {
  font-size: 15px;
}

#p {
  margin: 10px;
  font-size: 25px;
}

#buttonadd {
  display: flex;
  justify-content: center;
  font-size: 12px;
  left: 40%;
  height: 20%;
  width: 20%;
  border-radius: 5px;
  border: none;
  color: #fff;
  font-size: 18px;
  font-weight: 500;
  letter-spacing: 1px;
  cursor: pointer;
  height: 45px;
  margin: 10px 0;
}

.inputBox {
  margin-bottom: 15px;
}
</style>
