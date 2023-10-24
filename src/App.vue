<template>
  <main class="relative w-screen h-screen bg-[url('https://4kwallpapers.com/images/wallpapers/macos-monterey-wwdc-21-stock-dark-mode-5k-3840x2160-5585.jpg')] bg-center bg-no-repeat bg-cover">
    <div ref="box" class="box w-1/2 h-1/2 translate-x-1/2 translate-y-1/2 absolute bg-full rounded-xl border-gray-100/10 border-[0.075rem] box-content flex flex-col overflow-hidden">
      <div @mousedown.prevent="elementDown($event)" @mousemove.prevent="elementMove($event)" @mouseup="elementStop()" @mouseleave="elementStop()" class="grid w-full h-9 p-3 bg-neutral-900/40 backdrop-blur rounded-t-xl">
        <div class="grid gap-2 grid-cols-3 w-fit">
          <div class="w-3 h-3 bg-red-500 rounded-full"></div>
          <div class="w-3 h-3 bg-amber-400 rounded-full"></div>
          <div class="w-3 h-3 bg-green-500 rounded-full"></div>
        </div>
      </div>
      <div class="w-full flex-grow-1 flex-1 bg-neutral-900/20 backdrop-blur-sm rounded-b-xl">
      </div>
    </div>
  </main>
</template>

<script>
import 'boxicons';
import './main.css';

let move = {
  active: false,
  x: 0,
  y: 0,
  newX: 0,
  newY: 0,
}

export default {
  name: 'App',
  methods: {
    elementDown(event) {
      move.x = event.clientX;
      move.y = event.clientY;
      move.active = true;
    },
    elementMove(event) {
      if (!move.active) return;

      let element = document.body.querySelector("div.box");

      move.newX = event.clientX;
      move.newY = event.clientY;

      element.style.left = `${element.offsetLeft - (move.x - move.newX)}px`;
      element.style.top = `${element.offsetTop - (move.y - move.newY)}px`;

      move.X = move.newX;
      move.Y = move.newY;
    },
    elementStop() {
      move.active = false;
    },
  },
  //   animations(heading, description, button) {
  //     setTimeout(()=> document.body.querySelector(`.${heading}`).classList.remove('-translate-y-10', 'opacity-0'), 50);
  //     setTimeout(()=> document.body.querySelector(`.${description}`).classList.remove('scale-0', 'opacity-0'), 750);
  //     setTimeout(()=> document.body.querySelector(`.${button}`).classList.remove('scale-0', 'opacity-0'), 1250);
  //   },
  //   click(link) {
  //     window.location.href=link;
  //   },
  // },
}
</script>

<style>
</style>
