<script setup>
const datas = [
  {
    img_desktop: "/images/desktop/image-deep-earth.jpg",
    img_mobile: "/images/mobile/image-deep-earth.jpg",
    title: "Deep earth",
  },
  {
    img_desktop: "/images/desktop/image-night-arcade.jpg",
    img_mobile: "/images/mobile/image-night-arcade.jpg",
    title: "Night arcade",
  },
  {
    img_desktop: "/images/desktop/image-soccer-team.jpg",
    img_mobile: "/images/mobile/image-soccer-team.jpg",
    title: "Soccer team VR",
  },
  {
    img_desktop: "/images/desktop/image-grid.jpg",
    img_mobile: "/images/mobile/image-grid.jpg",
    title: "The grid",
  },
  {
    img_desktop: "/images/desktop/image-from-above.jpg",
    img_mobile: "/images/mobile/image-from-above.jpg",
    title: "From up above VR",
  },
  {
    img_desktop: "/images/desktop/image-pocket-borealis.jpg",
    img_mobile: "/images/mobile/image-pocket-borealis.jpg",
    title: "Pocket borealis",
  },
  {
    img_desktop: "/images/desktop/image-curiosity.jpg",
    img_mobile: "/images/mobile/image-curiosity.jpg",
    title: "The curiosity",
  },
  {
    img_desktop: "/images/desktop/image-fisheye.jpg",
    img_mobile: "/images/mobile/image-fisheye.jpg",
    title: "Make it fisheye",
  },
];
</script>
<template>
  <section class="px-5 md:px-[10rem] py-[4rem] relative mt-[5rem]">
    <div class="flex justify-between items-center">
      <div class="text-center md:text-left">
        <h1 class="text-4xl md:text-6xl uppercase">Our creations</h1>
      </div>
      <div class="absolute bottom-0 md:static left-32 md:left-auto">
        <button
          class="border border-black py-2 px-10 cursor-pointer uppercase tracking-widest bg-white hover:bg-black hover:text-white"
        >
          See all
        </button>
      </div>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-4 gap-5 pt-16">
      <div
        class="relative group overflow-hidden"
        v-for="(data, index) in datas"
        :key="index"
      >
        <figure class="w-full">
          <picture>
            <source media="(min-width: 768px)" :srcset="data.img_desktop" />
            <img class="w-full" :src="data.img_mobile" :alt="data.title" />
          </picture>
        </figure>

        <div
          class="absolute inset-0 bg-white/0 transition duration-300 group-hover:bg-white/40"
        ></div>

        <div class="absolute inset-x-0 bottom-0 p-7 flex items-end">
          <h2
            class="w-[14rem] text-5xl text-white group-hover:text-black font-light"
          >
            {{ data.title }}
          </h2>
        </div>
      </div>
    </div>
  </section>
</template>
