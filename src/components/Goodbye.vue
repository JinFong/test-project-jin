<template>
  <div class="Goodbye">

    <h1>{{ message }}</h1>

    <div>
      <h2>Goodbye {{fullname}}</h2>
      <label>First Name:</label>
      <input type = "text" class ="form-control" v-model = "first"/>
      <br>
      <br>
      <label>Last Name:</label>
      <input type = "text" class ="form-control" v-model = "last"/>

    </div>

  </div>
</template>

<script>
export default {
  name: 'Goodbye',
  data () {
    return {
      msg: '',
      message: 'This is a Goodbye component test...',
      count: 10,
      first: '',
      last: '',
      itemsInStock: 10,
      isA: true,
      isB: true,


    }
  },

  methods: {
    countUp: function() {
      this.count += 10;
    },

    countDown: function() {
      this.count -= 10;
    },

  },

  computed: {
      level: function() {
        if (this.count >= 200) {
          return "Pro";
        } else if (this.count >= 100) {
          return "Intermediate";
        } else if (this.count >= 0) {
          return "Beginner";
        } else {
          return "Banned";
        }
      },

      fullname: {
        //getter function
        get: function(){
          return this.first + " " + this.last;
        },
        //setter function
        set: function(value){
          var name = value.split(' ');
          this.first = name[0];
          this.last = name[name.length -1];
        },
      },

  },

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
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

.class-a {
  color: #FF0000;
}

.class-b {
  color: green;
  text-decoration: underline;
}

</style>
