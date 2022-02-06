<template>
  <div>
    <form>
      <v-select
      v-model="subject"
      :items="items"
      label="--เลือกวิชา--"
      style="margin: 10px"
    ></v-select>
    <v-text-field
      v-model="work"
      label="ชื่องาน"
      style="margin: 10px"
      outlined
    ></v-text-field>
    <v-btn id="buttonadd" color="success" class="mr-4" @click="add"
      >เพิ่มงาน</v-btn
    >
    </form>
    
    
  </div>
</template>

<script>
export default {
  data() {
    return {
      subject: "",
      work: "",
      items: ["วิชา Web: ", "วิชา SA: ", "วิชา ML: ", "วิชา ENG: ","วิชา COMSCI: ","วิชา สุขภาพ: ","วิชา สถิติ: ","อื่นๆ: "],  
    };
  },

  methods: {
    add() {
      this.$emit("rtb",{ text: this.subject + this.work });
    },
  },
};
</script>

<style></style>
