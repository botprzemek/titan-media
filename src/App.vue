<template>
    <main class="z-10 w-screen h-screen relative grid place-content-center select-none">
      <section class="grid place-items-center overflow-hidden">
        <h1 class="heading -translate-y-10 opacity-0 transform-gpu transition-all ease-out duration-700 text-white font-bold text-6xl text-center pt-10 mb-1">Titan Media</h1>
        <p class="description opacity-0 transition-all ease-out duration-1000 rounded-xl backdrop-blur-md bg-white/10 text-white text-md text-center mb-5 py-2 w-full">Strona jest w trakcie tworzenia.</p>
        <button @click="click('mailto:robert.szymanski@titanmedia.pl')" aria-label="Kliknij, aby uzyskać kontakt" title="Kliknij, aby uzyskać kontakt" class="button scale-0 opacity-0 transform-gpu transition-all ease-out duration-1000 backdrop-blur-md bg-white/10 aspect-square p-1 rounded-full grid place-items-center animate-bounce w-fit">
          <box-icon class="aspect-square fill-white border-b-0" type="solid" name="info-circle" size="md"></box-icon>
        </button>
      </section>
    </main>
    <div class="z-0 inset-0 absolute h-screen w-screen bg-scroll animate-gradient bg-full bg-gradient-to-bl from-indigo-400 to-blue-600"></div>
</template>

<script>
import 'boxicons';
import './main.css';

export default {
  name: 'App',
  methods: {
    animations(heading, description, button) {
      setTimeout(()=> document.body.querySelector(`.${heading}`).classList.remove('-translate-y-10', 'opacity-0'), 50);
      setTimeout(()=> document.body.querySelector(`.${description}`).classList.remove('scale-0', 'opacity-0'), 750);
      setTimeout(()=> document.body.querySelector(`.${button}`).classList.remove('scale-0', 'opacity-0'), 1250);
    },
    click(link) {
      window.location.href=link;
    },
  },
  mounted() {
    this.animations('heading', 'description', 'button');
  }
}
</script>

<style>
</style>
