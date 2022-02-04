<template>
  <div>
    <section class="sec-100vh flexbox align-center justify-center w-75">
      <div id="about" class="half">
        <h1 class="color-black font-size-5-5em nomargin"> MetaDrivers </h1>
        <p class="margin top px20 font-size-1-5em line-height-1-5em">
          MetaDrivers is a collection of recent and historical formula 1 drivers made in PixelArt. <br>
          This collection includes my passion for F1 and NFT. All drivers are 32x32 pixels. Join the project and get your favorite driver! <br>
          The collection will be updated periodically.
        </p>
        <button class="simple font-size-1em w-200px" onclick="location.href='https://opensea.io/collection/metadrivers-collection';">
          OpenSea <img style="filter: invert(1)" class="margin left px10" src="@/assets/opensea-dark.svg" />
        </button>
      </div>
      <div class="half flexbox justify-end">
        <img v-bind:src="img" class="border-radius-px10"/>
      </div>
    </section>
    <section class="flexbox  w-75">
      <div class="one-third text-center margin bottom px20">
        <p class="margin top px20 font-size-2em line-height-1-5em text-justify text-center font-weight-bolder">
          Base
        </p>
        <img src="@/assets/img/vettel.png" class="border-radius-px10 img-vw-20"/>
      </div>
      <div class="one-third text-center margin bottom px20">
        <p class="margin top px20 font-size-2em line-height-1-5em text-justify text-center font-weight-bolder">
          World Champion
        </p>
        <img src="@/assets/img/verstappen.jpg" class="border-radius-px10 img-vw-20"/>
      </div>
      <div class="one-third text-center margin bottom px20">
        <p class="margin top px20 font-size-2em line-height-1-5em text-justify text-center font-weight-bolder">
          Historical
        </p>
        <img src="@/assets/img/schumacher.png" class="border-radius-px10 img-vw-20"/>
      </div>
    </section>
  </div>
</template>

<script lang="ts">
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
  setup() {

    const nfts = ["schumacher.png", "verstappen.jpg", "vettel.png", "alonso.png", "bottas.png", "gasly.png", "giovinazzi.png", "hamilton.png", "latifi.png", "leclerc.png", "mazepin.png", "norris.png", "ocon.png", "perez.png", "raikkonen.png", "ricciardo.png", "russell.png", "sainz.png", "schumacher-jr.png", "stroll.png", "tsunoda.png"];
    
    let img = `@/assets/img/${nfts[0]}`;
    let i = 0;

    setInterval(() => {
      
      img = `@/assets/img/${nfts[i++]}`

    }, 2000)

    return{

      img

    }

    
  }
})
</script>

<style lang="scss">

  @import url('https://fonts.googleapis.com/css2?family=Outfit:wght@600&family=Source+Sans+Pro:wght@300;400&display=swap');

  $black: #3d3d3d;
  $blue: #3742fa;
  $white: #fefefe;
  $hover-color: #fa3741;

  body{
    margin: 0;
  }
  h1,h2,h3,h4,h5,h6{ 
    font-family: 'Outfit', sans-serif; 
  }
  p, span{ font-family: 'Source Sans Pro', sans-serif; }

  .color-black{
    color: $black;
  }
  .font-size-2em{
    font-size: 2em;
  }
  .font-size-3-5em{
    font-size: 3.5em;
  }
  .font-size-5-5em{
    font-size: 5.5em;
  }
  .font-size-1em{
    font-size: 1em;
  }
  .font-size-1-5em{
    font-size: 1.5em;
  }
  .font-weight-lighter{
    font-weight: lighter;
  }
  .font-weight-bolder{
    font-weight: bolder;
  }
  .line-height-1-5em{
    line-height: 1.5em;
  }
  .half{
    width: 50%;
  }
  .one-third{
    width: 33%;
  }
  .text-justify{
    text-align: justify;
  }
  .text-center{
    text-align: center;
    &.align-center{
      align-items: center;
    }
  }

  .img-vw-20{
    width: 20vw;
    height: 20vw;
  }
  
  .nomargin{
    margin: 0;
  }
  .margin{
    &.top{
      &.px20{
        margin-top: 20px;
      }
      &.px10{
        margin-top: 10px;
      }
    }
    &.bottom{
      &.px20{
        margin-bottom: 20px;
      }
      &.px10{
        margin-bottom: 10px;
      }
    }

    &.left{
      &.px20{
        margin-left: 20px;
      }
      &.px10{
        margin-left: 10px;
      }
    }

    &.right{
      &.px20{
        margin-right: 20px;
      }
      &.px10{
        margin-right: 10px;
      }
    }
  }

  .border-radius-px10{
    border-radius: 10px;
  }

  .flexbox{
    display: flex;
    &.justify-center{
      justify-content: center;
    }
    &.justify-end{
      justify-content: flex-end;
    }
    &.align-center{
      align-items: center;
    }
  }

  section{
    margin: 0 auto;
    &.w-75{
      width: 75%;
    }
    &.sec-100vh{
      height: 100vh;
    }
  }

  button{
    &.simple{
      border-radius: 5px;
      border: none;
      padding: 20px;
      background: $blue;
      color: $white;
      transition-duration: 0.3s;
      &:hover{
        background: $hover-color;
      }
    }
    &.w-300px{
      width: 200px;
    }
  }

</style>

