<template>
  <div class="hello">
    <div class="card">
    <h1>{{ msg }}</h1>
    <p id="first" v-if="abonnes == 0">Acun abonnés pour le moment 😥 !!</p>
    <p id="second" v-else-if="abonnes == 1">Une Personne sur notre chaine, c'est un bon début 💪 !!  </p>
    <p id="third" v-else>{{abonnes}} Personnes sur notre chaine 🔥 !!</p>
    <button v-on:click="subscribe()">Subscribe ❤️ !</button>
    </div>
    <div class="comment" v-for="(comment,index) in comments" v-bind:key="index">
      <h3>{{comment.nom}}</h3>
      <p>{{comment.commentaire}}</p>
      <div v-if="comment.note >=5">
      <span v-for="i in comment.note" v-bind:key="i">⭐</span>
      </div>
      <span v-else>💩</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,

  },
  data: function (){
    return {
      abonnes:0,
      comments:[{
        nom:'Glei Jihed',
        commentaire:" C'est la bombe ! ",
        note: 8},
        {
          nom:'Dinamo MAC',
          commentaire:" C'est magnifique !!",
          note: 7},
        {
          nom:'Alberb Diouf',
          commentaire:" C'est du caca ! ",
          note: 1
      }]
    }

  },
  methods: {
    subscribe: function (){
      this.abonnes++;
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
#first{
  color:red;
  font-family: "Arial Black";
  font-size: 25px;
  cursor: none;

}
#second {
  color:yellow;
  font-family: "Arial Black";
  font-size: 25px;
  cursor: auto;
}
#third {
  color:limegreen;
  font-family: "Arial Black";
  font-size: 25px;
  cursor: auto;
}
.card {
  cursor:auto;
  margin-left: auto;
  margin-right: auto;
  background-color:white;
  border-width:2px;
  border-style:solid;
  border-color:black;
  width: 600px;
  height: 300px;
  margin-top: 15px;
  box-shadow: 25px 25px 44px rgba(103, 101, 101, 0.03);
  border-radius: 6px ;
}
.card:hover{
  box-shadow: 10px 10px 54px rgba(33, 33, 33, 0.6);
}
button {
  width: 120px;
  height: 60px;
  color: yellow;
  background-color: red;
  border-radius: 6px;
  border-color: white;
  cursor: pointer;
}
.comment {
  width: 600px;
  height: 150px;
  cursor:auto;
  margin-left: auto;
  margin-right: auto;
  background-color:white;
  border-width:2px;
  border-style:solid;
  border-color:black;
  margin-top: 15px;
  box-shadow: 25px 25px 44px rgba(103, 101, 101, 0.03);
  border-radius: 6px ;

}
.comment:hover{
  box-shadow: 10px 10px 54px rgba(33, 33, 33, 0.6);
}
</style>
