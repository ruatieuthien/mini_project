<template>
  <div class="containers">
  <div class="group_button">
    <!-- <li data-tabs="content_stored" class="on">Stored Resource</li>
    <li data-tabs="content_add">Add Resource</li> -->
    
  </div>
  </div>
</template>

<script>

export default {
  name: "StoredResource",
  props: {
    msg: String,
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
.group_button{
  border-radius: 12px;
  
  padding: 1rem;
  margin: 2rem auto;
  width: 850px;
  display:  flex;
  flex-direction: row;
}
/* .group_button {
   padding: 10px 26px;
   text-transform: uppercase;
   font-weight: 700;
   text-decoration: none;
   list-style: none;
} */
</style>
