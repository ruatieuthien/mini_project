<template>
  <div class="containers">
    <div class="form_title">
    <li id="form_normal" class="level">
    </li>
    <li id="form_hard"  class="level">
      <div class="form_control">
        <label for="title">Title</label>
        <input id="title" name="title" type="text" v-model="title">
      </div>
      <div class="form_control">
        <label for="title">Description</label>
        <textarea id="description" name="description" type="text" v-model="description"></textarea>
      </div>
      <div class="form_control">
        <label for="link">Link</label>
        <input id="link" name="link" type="url" v-model="link">
      </div>
      <div class="btn_add">
        <button class="" type="submit" @click="addItems">Add Resource</button>

      </div>
    </li>
    </div>
  </div>
</template>

<script>

export default {
  name: "AddResource",
  props: {
    msg: String,
  },
  data(){
    return{
      title: "",
      description: "",
      link: "",
      items: [],
    };
  },
  methods: {
    addItems() {
      let newItems = {
        id: new Date(),
        title: this.title,
        description: this.description,
        link: this.link,
      };
      this.items.push(newItems);
      if(!localStorage.getItem("items")){
        localStorage.setItem("items", JSON.stringify(this.items));
      }else {
        let allItems = JSON.parse(localStorage.getItem("items"));
        allItems.unshift(newItems);
        localStorage.getItem("items", JSON.stringify(allItems));
      }
    },
  }
};

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.containers{
    width: 100%;
    max-width: 1260px;
  margin: 0 auto;
}
li{
    list-style: none;
}
.form_title{
  display: flex;
  flex-direction: column;
}
.form_control{
  margin: 1rem 0;
}
label{
  font-weight: 700;
  display: block;
  margin-bottom: 0.5rem;
  font-size: 30px;
  display: flex;
  justify-content: flex-start;
}
#title{
  display: block;
  width: 100%;
  font: inherit;
  height: 40px;
  border: 1px solid #ccc;
}
#description{
  display: block;
  width: 100%;
  height: 80px;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
}
#link{
      display: block;
    width: 100%;
    font: inherit;
    padding: 0.15rem;
    height: 40px;
    border: 1px solid #ccc;
}
.btn_add{
  margin-top: 25px;
  display: flex;
  justify-content: flex-start;
}
button{
  padding: 1rem 1.5rem;
    font-family: inherit;
    background-color: #3a0061;
    border: 1px solid #3a0061;
    color: #fff;
    cursor: pointer;
} 
</style>