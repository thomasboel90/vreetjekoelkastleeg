<template>
    <div class="container">
      <form @submit.prevent="addIngredient">
        <input type="text" placeholder="Enter an ingredient you have." v-model="ingredient">
    {{ ingredient }}
        </form>
    <ul>
      <li v-for="(data, index) in ingredients" :key='index'>{{data.ingredient}}</li>
    </ul>
      <p>These are the ingredients in your fridge.</p>
    </div>
</template>

<script>
export default {
  name: 'Ingredients',
  data() {
    return {
      ingredient: '',
      ingredients: [
        {'ingredient': 'tomato'},
        {'ingredient': 'cucumber'},
        {'ingredient': 'chicken'},
        {'ingredient': 'rice'}
      ]
    }
  },
  methods : {
      addIngredient(){
          this.ingredients.push({ingredient: this.ingredient});
          this.ingredient = '';
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .holder {
    background: #fff;
  }
  ul {
    margin: 0;
    padding: 0;
    list-style-type: none;
  }
  ul li {
    padding: 20px;
    font-size: 1.3em;
    background-color: #E0EDF4;
    border-left: 5px solid #3EB3F6;
    margin-bottom: 2px;
    color: #3E5252;
  }
  p {
    text-align:center;
    padding: 30px 0;
    color: gray;
  }
  .container {
    box-shadow: 0px 0px 40px lightgray;
  }
  input {
    width: calc(100% - 40px);
    border: 0;
    padding: 20px;
    font-size: 1.3em;
    background-color: #323333;
    color: #687F7F;
  }
</style>
