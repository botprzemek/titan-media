<template>
    <main class="z-10 w-screen h-screen relative grid place-content-center">
      <div class="grid place-items-center overflow-hidden">
        <h1 class="heading -translate-y-10 opacity-0 transform-gpu transition-all ease-out duration-700 text-white font-bold text-6xl text-center mb-4 pt-10">Titan Media</h1>
        <button class="button scale-0 opacity-0 transform-gpu transition-all ease-out duration-700 backdrop-blur-md bg-white/10 aspect-square p-1 rounded-full grid place-items-center animate-bounce w-fit">
          <box-icon class="aspect-square fill-white border-b-0"  type="solid" name="down-arrow-circle" size="md"></box-icon>
        </button>
      </div>
    </main>
    <div class="z-0 inset-0 absolute h-screen w-screen bg-scroll animate-gradient bg-full bg-gradient-to-bl from-indigo-400 to-blue-600"></div>
</template>

<script>
import 'boxicons';
import './main.css';

export default {
  name: 'App',
  methods: {
    animations(heading, button) {
      setTimeout(()=> document.body.querySelector(`.${heading}`).classList.remove('-translate-y-10', 'opacity-0'), 50);
      setTimeout(()=> document.body.querySelector(`.${button}`).classList.remove('scale-0', 'opacity-0'), 750);
    },
  },
  mounted() {
    this.animations('heading', 'button');
  }
}
</script>

<style>
</style>
