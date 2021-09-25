<template>
  <div id="first">
    <!--javascript convention -->
    <img :class="gender" :src="picture" :alt="` ${firstName} ${lastName}`" />
    <!--{{}} this renders data-->
    <h1>{{ firstName }} {{ lastName }}</h1>
    <p>{{ email }}</p>
    <!--next task click on this button and get some event-->
    <v-btn @click="getUser()" :class="gender">Print</v-btn>
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
let url = "https://via.placeholder.com/600/51aa97";
//export by default otherwise need to export explicitly
export default {
  el: "#first", //should match div id to render everything.
  name: "HelloWorld",
  props: ["msg"],
  data() {
    return {
      firstName: "Goku",
      lastName: "Son",
      email: "goku@gmail.com",
      gender: "male",
      picture: url,
    };
  },
  methods: {
    async getUser() {
      const res = await fetch("https://randomuser.me/api");
      // or directly data in json
      const data = await res.json();
      // or directly fetch result like const {results}=await res.json()
      console.log(data);

      (this.firstName = data.results[0].name.first),
        (this.lastname = data.results[0].name.last),
        (this.email = data.results[0].email),
        (this.gender = data.results[0].gender),
        (this.picture = data.results[0].picture.large);
      console.log("Hi i am Punch man !" + this.firstName);

      /* This gives static data so building async await to fetch data from api and display randomly
     this.firstName ='Sakuru',
      this.lastname = 'chan',
      this.email = 'sakura@outlook.com',
      this.gender = 'female',
      this.picture = 'https://randomuser.me/api/portraits/med/women/53.jpg'
      console.log("Hi i am Punch man !" + this.firstName);  */
    },
  },
};
</script>

<style scoped>
.first {
  text-align: center
}
img {
  border-radius: 50%;
  border: 5px #333 solid;
  max-width: 100px;
  max-height: 100px;
}
.male {
  border-color: rgb(7, 199, 224);
  background-color: rgb(7, 199, 224);
}
.female {
  background-color: rgb(228, 12, 131);
  border-color: rgb(228, 12, 131);
}
.v-btn {
  padding: 5px 10px 5px 10px; /*top right bottom left*/
}
</style>
