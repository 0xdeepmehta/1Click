<template>
  <div class="">
    <!-- <Nav /> -->

    <Hero/>
    
    <Demo/>
    <Pricing />

    <HowItWork/>
    <Feature/>
    <Testimonial/>
    <Footer/>
  </div>
</template>

<script>
export default {};
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
body {
  @apply bg-background;
}
.active {
  @apply fill-current; 
  @apply text-white; 
  @apply cursor-pointer;
}
</style>
