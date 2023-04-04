<template>
  <NavBar />
  <div class="main-div">
    <div id="iteration-2">
      <h2> · ITERATION 2 ·</h2>
      <div class="border-div" :class="{ active: activebtn }">
        <p class="p-instructions">Display the result of a JavaScript operation in a component's HTML</p>
        <p><strong>First</strong>, you just need to insert a mathematical operation inside your HTML and see what
          happens.
          Something as
          simple as 2 + 2 is enough here.<br>
          The result of 2 + 2 is <span>{{ 2 + 2 }}</span></p>

        <p><strong>Then</strong>, the real challenge begins: you have to "print" a string on your template, with a twist:
          this string has
          to be returned by a function and read the data stored in other reactive variables</p>

        <p><span>{{ getTitle }}</span> --This is the titles of Iteration 4</p>
      </div>
      <div id="iteration-3">
        <h2>· ITERATION 3 ·</h2>
        <div class="border-div">
          <p class="p-instructions">Show an element only if a particular property is set to true</p>
          <button v-on:click="show = !show">
            Mostrar/Ocultar Iteration 4
          </button>

          <div v-show="show" id="iteration-4">
            <h2>· ITERATION 4 ·</h2>
            <div class="border-div">
              <IterarionFour v-for="film in films" :key="film.index" :title="film.title" :description="film.description"
                :content="film.content" />
            </div>
          </div>
        </div>
      </div>
      <div id="iteration-5">
        <h2>· ITERATION 5 ·</h2>
        <div class="border-div">
          <button>¡Change Iteration 2 background color!</button>
        </div>
      </div>

    </div>

    <FooterComp />
  </div>
</template>

<script setup>
import NavBar from './components/NavBar.vue'
import FooterComp from './components/FooterComp.vue'
import IterarionFour from './components/IterationFour.vue'
import { reactive, ref, computed } from "vue";


const show = ref(false);
const activebtn = ref(false);


const films = reactive([
  {
    index: 0,
    title: "The Godfather",
    description: "directed by Francis Ford Coppola",
    content: "Epic tale of a 1940s New York Mafia family and their struggle to protect their empire from rival families as the leadership switches from the father (Marlon Brando) to his youngest son (Al Pacino). Vito Corleone (Marlon Brando) is The Godfather, the Don (head) of a successful, tightly-knit family whose business is organized crime...",
  },
  {
    index: 1,
    title: "The Godfather: Part II",
    description: "Directed by Francis Ford Coppola",
    content: `Continuing saga of the Corleone family as they move to Nevada and make the casino business their major income source under the leadership of the increasingly paranoid and malevolent Michael, whose reign as the "Don" is juxtaposed against the parallel tale of his father's escape from Sicily as a young boy and his subsequent rise to power in New York's Lower East Side during the turn-of-the-century.`,
  },
  {
    index: 2,
    title: "12 Angry Men",
    description: "Directed by Sidney Lumet",
    content: "Eleven jurors are convinced that the defendant is guilty of murder. The twelfth has no doubt of his innocence. How can this one man steer the others toward the same conclusion?",
  },])


const getTitle = computed(() => {
  const titles = [];
  for (let i = 0; i < films.length; i++) {
    titles.push(films[i].title);
  }

  return titles;
},)

console.log(getTitle)
</script>

<style scoped>
h2 {
  font-weight: 500px;
  font-size: 16px;
  padding: 0 20px;
  margin-bottom: 0;
}



span {
  font-weight: 700;
}

.main-div {
  background-color: #FFe6FF;
  padding: 20px;
  margin: 0;
}

.border-div {
  border: 5px solid black;
  padding: 20px;
  margin: 0 20px 20px 20px;
  background-color: white;
}

button {
  font-family: 'Courier New', Courier, monospace;
}

button:hover {
  border: 2px solid black;
  background-color: #ff00ff;
  font-weight: 500;
}

.activebtn {
  background-color: aquamarine;
}

.btn-rest {
  background-color: white;
}
</style>
