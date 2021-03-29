<template>
  <div class="page">
    <Navbar />
    <Content/>
  </div>
</template>

<script>
import Navbar from './Navbar.vue';
import Content from './Content.vue';

export default {
  name: 'Workspace',
  components: {
    Navbar,
    Content
  }
}
</script>
  
<style lang="scss">
@font-face {
    font-family: NovaPoshta;
    /* Гарнитура шрифта */
    src: url(../fonts/NovaPoshta-Regular.woff2);
    /* Путь к файлу со шрифтом */
}

@font-face {
    font-family: NovaPoshtaBold;
    /* Гарнитура шрифта */
    src: url(../fonts/NovaPoshta-Bold.woff2);
    /* Путь к файлу со шрифтом */
}

@font-face {
    font-family: NovaPoshtaBlack;
    /* Гарнитура шрифта */
    src: url(../fonts/NovaPoshta-Black.woff2);
    /* Путь к файлу со шрифтом */
}


* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    color: #202124;
    font-family: 'NovaPoshta', sans-serif;
}

.page {
    background: #E0E0E0;
    padding-bottom: 50px;
    display: flex;
    flex-direction: column;
    align-items: center;
    min-height: 100vh;
    overflow-x: hidden;
}
</style>


