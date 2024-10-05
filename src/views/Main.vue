<template>
  <div id="header">
    <svg xmlns="http://www.w3.org/2000/svg" class="header-curve" xmlns:xlink="http://www.w3.org/1999/xlink" width="527" height="983" viewBox="0 0 527 983">
      <defs>
        <clipPath id="clip-path">
          <rect id="Rectangle_28" data-name="Rectangle 28" width="527" height="983" transform="translate(1393)" fill="#fff" stroke="#707070" stroke-width="1"/>
        </clipPath>
      </defs>
      <g id="main-curve" transform="translate(-1393)" clip-path="url(#clip-path)">
        <path id="Path_19" data-name="Path 19" d="M1923.515-76.558s174.1,154.948,191.507,316.871S2053,425.154,1993.154,571.133s-40.26,168.9-117.516,253.1-117.146,103.631-191.507,83.7-239.384,1.993-287.261-251.1,95.754-761.287,95.754-761.287Z" transform="translate(37 42.405)" fill="#ebebeb"/>
      </g>
    </svg>
    <div class="container" id="header-content">
      <div class="code-background" :style="'background-image: url(\'' + code_background + '\')'"></div>
      <div class="header-right">
        <picture>
          <img src="~@/assets/images/hamedmoody-curved.png" alt="Hamed Moodi" width="562" height="732">
        </picture>
        <div class="float-cursor float-cursor-php">
          <svg id="mouse-pointer" xmlns="http://www.w3.org/2000/svg" width="37.97" height="38.937" viewBox="0 0 37.97 38.937">
            <g id="Group_1" data-name="Group 1" transform="translate(0 0)">
              <path id="Path_7" data-name="Path 7" d="M19.841,38.937l.116,0a2.105,2.105,0,0,0,1.906-1.512l3.809-13.008,13.91-2.757a2.107,2.107,0,0,0,.559-3.938L6.383.236A2.106,2.106,0,0,0,3.47,2.914L17.9,37.638A2.1,2.1,0,0,0,19.841,38.937Z" transform="translate(-3.309 0)" fill="#6d73e0"/>
            </g>
          </svg>
          <div class="float-cursor-content">
            <img src="~@/assets/images/php-small-icon.png" alt="PHP" width="68" height="68">
            PHP Programmer
          </div>
        </div>
        <div class="float-cursor float-cursor-wp">
          <svg id="mouse-pointer" xmlns="http://www.w3.org/2000/svg" width="37.97" height="38.937" viewBox="0 0 37.97 38.937">
            <g id="Group_1" data-name="Group 1" transform="translate(0 0)">
              <path id="Path_7" data-name="Path 7" d="M19.841,38.937l.116,0a2.105,2.105,0,0,0,1.906-1.512l3.809-13.008,13.91-2.757a2.107,2.107,0,0,0,.559-3.938L6.383.236A2.106,2.106,0,0,0,3.47,2.914L17.9,37.638A2.1,2.1,0,0,0,19.841,38.937Z" transform="translate(-3.309 0)" fill="#6d73e0"/>
            </g>
          </svg>
          <div class="float-cursor-content">
            <img src="~@/assets/images/wp-small-icon.png" alt="WP" width="76" height="76">
            Wordpress Developer
          </div>
        </div>
      </div>
      <div class="header-left">
        <h1>حامد مودی</h1>
        <p class="header-subtitle">
          و وردپرس PHP متخصص برنامه نویسی
        </p>
        <div class="header-text">
          <p>
            بنده حامد مودی، برنامه نویس PHP و افزونه نویس و طراح قالب وردپرس و مدرس دوره های دانشجویار هستم
          </p>
          <p>
            از بین فریم ورک ها و Cms ها رفتم سراغ وردپرس و به صورت تخصصی در حوزه Plugin Development و Theme Development فعالیت کردم.
          </p>
          <p>
            شیوه تدریس بنده هم از پایه با ارائه جزئیات که سعی میکنم کامل یه موضوعی رو پله پله به مخاطب انتقال بدم
          </p>
        </div>
        <a href="https://www.daneshjooyar.com/teacher/hamedmoody/" class="see-courses" target="_blank">
          <svg xmlns="http://www.w3.org/2000/svg" width="30.098" height="34.524" viewBox="0 0 30.098 34.524">
            <path id="Polygon_1" data-name="Polygon 1" d="M13.792,6.05a4,4,0,0,1,6.94,0L31.088,24.108a4,4,0,0,1-3.47,5.99H6.905a4,4,0,0,1-3.47-5.99Z" transform="translate(30.098) rotate(90)" fill="#fff"/>
          </svg>
          دوره های آموزشی من
        </a>

        <div class="ide">
          <div class="ide-header">
            <div class="ide-dots">
              <span></span>
              <span></span>
              <span></span>
            </div>
            <div class="ide-title">index.php</div>
          </div>
          <div class="ide-content">
            &lt;?php echo 'Hamed Moodi';
          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<script>
import code_background from '@/assets/images/Header-backround.png';
export default {
  name: "Main",
  data() {
    return {
      code_background: code_background,
    }
  },
  mounted() {
    this.start_cursor_animate();
  },
  methods: {
    start_cursor_animate(){
      let cursors = document.querySelectorAll( '.float-cursor' );
      if( cursors ){
        for( let i = 0; i < cursors.length; i++ ){
          let cursor = cursors[i];
          this.cursor_animate( cursor );
        }
      }
    },
    cursor_animate( cursor_el ){

      let min               = 20;
      let max               = 80;
      let rand_left         = Math.floor(Math.random() * (max - min + 1) + min);
      let rand_top          = Math.floor(Math.random() * (max - min + 1) + min);
      let rand_time         = Math.floor(Math.random() * (10 - 5 + 1) + 3);

      let left_style            = rand_left + '%';
      let top_style             = rand_top + '%';

      if( window.innerWidth <= 768 && rand_left > 50 ){
        left_style  = `calc( ${left_style} - 200px )`;
      }

      cursor_el.style.left  = left_style;
      cursor_el.style.top   = top_style;

      setTimeout( this.cursor_animate, rand_time * 1000, cursor_el );

    },

  }
}
</script>

<style scoped lang="scss">
  #header{
    position: relative;
    overflow: hidden;
    .header-curve{
      position: absolute;
      width: 300px;
      height: auto;
    }
    #header-content{
      position: relative;
      z-index: 2;
      display: grid;
      //grid-template-columns: 440px auto;
      align-items: center;
      gap: 30px;
      .code-background{
        content: "";
        position: absolute;
        left: 0;
        top: 0;
        bottom: 0;
        right: 0;
        background-repeat: no-repeat;
        background-position: left center;
        opacity: .1;
        z-index: -1;
      }
    }
    .header-right{
      position: relative;
      text-align: center;
      picture{
        img{
          max-width: 100%;
          height: auto;
        }
      }
    }
    .header-left{
      h1{
        font-weight: bold;
        font-size: 42px;
      }
      .header-subtitle{
        color: #989898;
      }
      .header-text{
        line-height: 200%;
        margin: 25px 0;
        p{
          margin-top: 15px;
        }
      }
      .see-courses {
        background: var(--color-primary);
        color: #FFF;
        text-decoration: none;
        border-radius: 40px;
        display: inline-flex;
        align-items: center;
        gap: 5px;
        padding: 5px 10px 5px 20px;
        box-shadow: 0 3px 6px rgba(0,0,0,.16);
        transition: 0.3s;
        &:hover{
          background: var(--color-primary-hover);
        }
      }
    }

    .float-cursor {
      position: absolute;
      direction: ltr;
      text-align: left;
      transition: .5s ease-in-out;
      &.float-cursor-php{
        top: 40%;
        left: 56%;
      }
      &.float-cursor-wp{
        top: 60%;
        left: 46%;
        .float-cursor-content{
          background: #DFFF00;
          color: black;
        }
        svg path{
          fill: #DFFF00;
        }
      }
    }

    .float-cursor-content {
      background: var(--color-primary);
      border: 1px solid #ffffff57;
      color: #FFF;
      padding: 7px 20px 7px 10px;
      border-radius: 40px;
      margin-left: 20px;
      box-shadow: 0 3px 6px rgba(0,0,0,.16);
      white-space: nowrap;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 5px;
      img{
        width: 32px;
        height: auto;
      }
    }


  }

  .ide {
    margin-top: 15px;
    direction: ltr;
    background: #151718;
    color: #FFF;
    border-radius: 15px;
    padding: 15px;
    .ide-header {
      display: flex;
      align-items: center;
      gap: 11px;
    }
    .ide-dots{
      display: flex;
      align-items: center;
      gap: 5px;
      position: relative;
      span {
        background: #FF5F56;
        width: 16px;
        height: 16px;
        display: inline-block;
        border-radius: 50%;
        &:nth-child(2) {
          background: #FFBD2E;
        }
        &:nth-child(3) {
          background: #27C93F;
        }
      }

      .ide-content {
        padding: 10px 0 0 10px;
      }
    }
  }

  @media screen and ( min-width: 996px ){
    #header #header-content{
      grid-template-columns: 360px auto;
    }
  }

  @media screen and ( min-width: 1366px ){
    #header #header-content{
      grid-template-columns: 440px auto;
    }
  }

</style>