<template>
  <div>
    <header id="navbar" class="w-85 position-fixed flexbox justify-between align-center">
      <span class="source-sans font-size-1-25em"> <b> MetaDrivers </b> </span>
      <div> 
        <a href="https://www.instagram.com/metadrivers.ig/"><font-awesome-icon class="fa-2x margin right px10" :icon="['fab', 'instagram']"/></a>
        <a href="https://twitter.com/DriversMeta"><font-awesome-icon class="fa-2x" :icon="['fab', 'twitter']"/></a>
      </div>
    </header>
    <section class="sec-100vh flexbox align-center justify-center w-85 wrap resp-display-block resp-margin top px100">
      <div id="about" class="half resp-w-100 resp-no-min-width">
        <h1 class="color-black font-size-5-5em nomargin resp-4-5em"> 
            <span style="display: inline-block; margin-right: -12.5px;"> Meta </span>
            <span> Drivers </span>
        </h1>
        <p class="margin top px20 font-size-1-5em line-height-1-5em resp-justify resp-3vw">
          MetaDrivers is a collection of recent and historical formula 1 drivers made in PixelArt. <br>
          This collection includes my passion for F1 and NFT. All drivers are 32x32 pixels. Join the project and get your favorite driver! <br>
          The collection will be updated periodically.
        </p>
        <button class="simple font-size-1em w-200px" onclick="location.href='https://opensea.io/collection/metadrivers-collection';">
          OpenSea <img style="filter: invert(1)" class="margin left px10" src="@/assets/opensea-dark.svg" />
        </button>
      </div>
      <div class="half flexbox justify-end resp-justify-center resp-w-100 resp-margin top px60 resp-no-min-width">
        <img v-bind:src="img" class="border-radius-px10 img-vw-30 min-width-300px resp-w-70"/>
      </div>
    </section>
    <section class="flexbox w-85 resp-display-block resp-w-100 resp-margin top px30">
      <div class="one-third text-center margin bottom px20 resp-w-100">
        <p class="margin top px20 font-size-2em text-justify text-center font-weight-bolder resp-1-5em resp-no-margin">
          Base
        </p>
        <img src="@/assets/img/vettel.png" class="border-radius-px10 img-vw-20 min-width-120px"/>
      </div>
      <div class="one-third text-center margin bottom px20 resp-align-center resp-w-100">
        <p class="margin top px20 font-size-2em line-height-1-5em text-justify text-center font-weight-bolder resp-1-5em resp-no-margin">
          World Champion
        </p>
        <img src="@/assets/img/verstappen.jpg" class="border-radius-px10 img-vw-20 min-width-120px"/>
      </div>
      <div class="one-third text-center margin bottom px20 resp-align-center resp-w-100">
        <p class="margin top px20 font-size-2em line-height-1-5em text-justify text-center font-weight-bolder resp-1-5em resp-no-margin">
          Historical
        </p>
        <img src="@/assets/img/schumacher.png" class="border-radius-px10 img-vw-20 min-width-120px"/>
      </div>
    </section>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from '@vue/composition-api'

export default defineComponent({
  setup() {

    const nfts = 
      [ 
        "schumacher.png", 
        "verstappen.jpg", 
        "vettel.png", 
        "alonso.png",
        "bottas.png", 
        "gasly.png",
        "giovinazzi.png", 
        "hamilton.png", 
        "latifi.png", 
        "leclerc.png", 
        "mazepin.png", 
        "norris.png", 
        "ocon.png", 
        "perez.png", 
        "raikkonen.png", 
        "ricciardo.png", 
        "russell.png", 
        "sainz.png", 
        "schumacher-jr.png", 
        "stroll.png", 
        "tsunoda.png"
      ].map(n => require(`@/assets/img/${n}`));
    
    const img = ref(nfts[0]);
    let i = 0;

    setInterval(() => {
      
      img.value = nfts[i++ % nfts.length];

    }, 1000)

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
  p{ font-family: 'Source Sans Pro', sans-serif; }
  .source-sans{
    font-family: 'Source Sans Pro', sans-serif;
  }
  
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
  .font-size-1-25em{
    font-size: 1.25em;
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
    min-width: 400px;
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

  a{
    color: $blue !important;
  }

  #navbar{
    height: 80px;
    top: 0;
    left: 0;
    right: 0;
    margin: auto;
    background: $white;
    // border-bottom: 1px solid $black;
  }
  .position-fixed{
    position: fixed;
  }


  .img-vw-20{
    width: 20vw;
  }
  .img-vw-40{
    width: 40vw;
  }
  .img-vw-30{
    width: 30vw;
  }
  .min-width-300px{
    min-width: 300px;
  }
  .min-width-120px{
    min-width: 120px;
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
    &.justify-between{
      justify-content: space-between;
    }
    &.justify-end{
      justify-content: flex-end;
    }
    &.align-center{
      align-items: center;
    }
    &.wrap{
      flex-wrap: wrap;
    }
  }

  .w-85{
    width: 85%;
  }
  section{
    margin: 0 auto;
    
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

  @media screen and (max-width: 940px){

    .resp-w-100{
      width: 100% !important;
    }
    .resp-w-70{
      width: 70% !important;
    }
    .resp-justify{
      text-align: justify !important;
    }
    .resp-1-5em{
      font-size: 1.5em;
    }
    .resp-3-5em{
      font-size: 3.5em;
    }
    .resp-4-5em{
      font-size: 4.5em;
    }
    .resp-display-block{
      display: block;
        &.resp-align-center{
          align-items: center;
        }
    }
    .resp-no-min-width{
      min-width: 0;
    }
    .resp-no-margin{
      margin: 0;
    }
    .resp-margin{
      &.top{
        &.px20{
          margin-top: 20px;
        }
        &.px30{
          margin-top: 30px;
        }
        &.px60{
          margin-top: 60px;
        }
        &.px100{
          margin-top: 100px;
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
    .flexbox{
      &.resp-justify-center{
        justify-content: center;
      }
      &.resp-align-start{
        align-items: flex-start;
      }
    }

  }

  @media screen and (min-width: 941px){

    .sec-100vh{
      height: 100vh;
    }
    
  }

</style>

