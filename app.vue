<script setup>
useHead({
  title: "Frontend Mentor | Loopstudios landing page",
  link: [
    {
      rel: "icon",
      type: "image/png",
      sizes: "32x32",
      href: "/images/favicon-32x32.png",
    },
  ],
});
</script>
<template>
  <div>
    <Header />
    <div class="py-[7rem]">
      <VrSection />
      <CreationSection />
    </div>
    <Footer />
  </div>
</template>
