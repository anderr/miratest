<template>
<div id="app" class="page">
  <div class="page__content">
    <TheHeader />

    <div class="container">
      <app-cards :card="card"></app-cards>
      <app-slider :card="card"></app-slider>
    </div>
  </div>

  <div id="footer" class="page__footer">
    © 2018 <a href="http://mirafox.com">Mirafox</a>
  </div>

  <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.7.2/css/all.css" integrity="sha384-fnmOCqbTlWIlj8LyTjo7mOUStjsKC4pOpQbqyi7RrhN7udi9RwhKkMHpvLbHG9Sr" crossorigin="anonymous">
</div>
</template>

<script>
import TheHeader from './components/TheHeader.vue'
import Cards from './components/Cards.vue'
import Slider from './components/Slider.vue'

export default {
  data() {
    return {
      card: {
        lorem: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ea tenetur praesentium blanditiis? Voluptate quam repudiandae, fuga, illum cupiditate iure architecto blanditiis eveniet possimus quidem quia id molestias reprehenderit iusto eaque!',
        user: 'userName userName user'
      },
    }
  },
  components: {
    appCards: Cards,
    appSlider: Slider,
    TheHeader,
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Cuprum:400,700&subset=cyrillic');

html {
  height: 100%;
}
body {
  background: #F4F4F4;
  height: 100%;
  padding: 0;
  margin: 0;
  font-family: 'Cuprum', sans-serif;
}
img {
  display: block;
}
* {
  box-sizing: border-box;
}

.page {
  display: flex;
  flex-direction: column;
  height: 100%;

  &__content {
    flex: 1 0 auto;
  }
  &__footer {
    flex: 0 0 auto;
    text-align: center;
    padding: 20px;
    border-top: 1px solid #DDD;
    font-size: 0.75em;
    color: #333;

    a {
      color: #333;
      text-decoration: none;
      border-bottom: 1px solid transparent;
      transition: 0.3s all;

      &:hover {
        color: #111;
        border-bottom: 1px solid #111;
      }
    }
  }
}

.container {
  max-width: 1200px;
  padding: 0 30px;
  margin: 0 auto;
  position: relative;
}

.rouble {
  position: relative;

  &:after {
    content: "–";
    position: absolute;
    bottom: -.15em;
    left: -.05em;
  }
}

.clearfix:after {
  content: "";
  display: table;
  clear: both;
}

.btn {
  float: none;
  display: block;
  background: #FFF;
  border: 1px solid #BBB;
  border-radius: 4px;
  width: 220px;
  margin: 10px auto;
  text-align: center;
  line-height: 40px;
  font-weight: bold;
  color: #666;
  cursor: pointer;
  outline: none;
  transition: background 0.3s;

  &:hover {
    background: darken(#FFF, 5%);
  }
}

.rotate180 {
  transform: rotate(180deg);
}
</style>
