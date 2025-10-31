<template>
  <div class="about-page">
    <div class="about-container">
      <div class="left">
        <div class="tama-frame">
          <img src="src/assets/dog-placeholder.png" alt="profile" class="tama-img" />
        </div>
      </div>

      <div class="right">
        <div class="dam-heading">
          <img src="~assets/name.png" alt="dam" class="dam-logo" />
        </div>

        <p class="intro-text">
           Hi! I am Dam. I love drawing, <strong>I'm 21 yo</strong>, and I'm an IT student at ESAN.
           You can use any pronouns for me. I also have a special talent — I can crack my thumbs!
        </p>


        <div class="socials">
          <a class="social" href="#" aria-label="Instagram"><q-icon name="mdi-instagram" size="36px" /></a>
          <a class="social" href="#" aria-label="Facebook"><q-icon name="mdi-facebook" size="36px" /></a>
          <a class="social" href="#" aria-label="Twitter"><q-icon name="mdi-twitter" size="36px" /></a>
          <a class="social" href="#" aria-label="LinkedIn"><q-icon name="mdi-linkedin" size="36px" /></a>
        </div>
      </div>
    </div>

  </div>

</template>

<style scoped lang="scss">
@import 'src/css/about.scss';
</style>

<script setup>
// Componente funcional vacío — garantiza que el SFC exporte un componente
// Puedes añadir props o lógica aquí si lo necesitas más tarde.
</script>
