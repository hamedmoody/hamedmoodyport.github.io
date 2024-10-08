<template>
  <div id="skill-rates">
    <div class="icon-background" :style="'background-image: url(\'' + icon_background + '\')'"></div>
    <div class="container rate-cols">
      <div class="rate-col-right">
        <h2>مهارت های من</h2>
        <svg xmlns="http://www.w3.org/2000/svg" width="512" height="190.284" viewBox="0 0 512 190.284">
          <path id="swirl-arrow-right-icon" d="M0,62.269c32.208,3.5,65.126,11.155,82.935,11.576,5.87.14,13.175-.651,5.825-3.929A172.989,172.989,0,0,0,27.3,55.625a147.983,147.983,0,0,0,15.993-4.683C86.208,36.225,134.457,27.248,181.6,27.186c39.015-.053,79.822,5.737,115.535,22.126A232.8,232.8,0,0,0,261.981,90.1c-21.629,32.107-31.567,79.665,13.75,96.773,37.675,14.221,72.262-18.318,76.731-54.787,3.222-26.29-6.915-45.475-19.352-63.408a92.8,92.8,0,0,0-19.168-20.1C406.881-16.9,494.724,26.293,512,117.511,507.09,5.165,386.456-21.164,306.068,42.942c-70.469-46-210.713-30.084-282.411,7.5C33.12,41.152,41.192,28,46.523,15.437c.79-1.859,4.569-8.993,4.29-12.878A2.387,2.387,0,0,0,48.465.006,3.973,3.973,0,0,0,45.6,1.356c-2.92,2.749-9.2,13.053-15.44,23.057C20.9,39.255,12.885,50.13,0,62.269ZM304.367,55.7a233.109,233.109,0,0,0-37.028,43.982c-16.542,25.678-22.453,56.275,1.472,72.95,14.806,10.319,30.931,9.682,44.76,1.389C363.379,144.146,339.318,77.023,304.367,55.7Z" transform="translate(0 0)" fill="#fff" fill-rule="evenodd"/>
        </svg>
      </div>
      <div class="rate-col-left">
        
        <div v-for="(skill, skill_index) in skills" class="rate" :key="skill_index">
          <picture>
            <img :src="skill.icon" :alt="skill.label" loading="lazy" width="64" height="64">
          </picture>
          <strong>{{skill.label}}</strong>
          <p>{{skill.amount}}%</p>
          <div class="amount">
            <div :style="{width: skill.amount + '%'}"></div>
          </div>
        </div>


      </div>
    </div>
  </div>
</template>

<script>
import icon_background from '@/assets/images/icon-background.png';
import icon_html from '@/assets/images/icons/icon-html.png'
import icon_css from '@/assets/images/icons/icon-css.png'
import icon_mysql from '@/assets/images/icons/icon-mysql.png'
import icon_wp from '@/assets/images/icons/icon-wp.png'
import icon_git from '@/assets/images/icons/icon-git.png'
import icon_php from '@/assets/images/icons/icon-php.png'
import icon_javascript from '@/assets/images/icons/icon-javascript.png'
import icon_xd from '@/assets/images/icons/icon-xd.png'
import icon_github from '@/assets/images/icons/icon-github.png'
import icon_vue from '@/assets/images/icons/icon-vue.png'

export default {
  name: "SkillRates",
  components: {},
  data(){
    return{
      icon_background: icon_background,
      skills: [
        {
          icon    : icon_php,
          label   : 'PHP',
          amount  : 99,
        },
        {
          icon    : icon_mysql,
          label   : 'MySQL',
          amount  : 80,
        },
        {
          icon    : icon_wp,
          label   : 'Wordpress',
          amount  : 94,
        },
        {
          icon    : icon_html,
          label   : 'Html',
          amount  : 95,
        },
        {
          icon    : icon_css,
          label   : 'Css',
          amount  : 88,
        },
        {
          icon    : icon_javascript,
          label   : 'JavaScript',
          amount  : 68,
        },

        {
          icon    : icon_git,
          label   : 'Git',
          amount  : 78,
        },
        {
          icon    : icon_github,
          label   : 'GitHub',
          amount  : 85,
        },
        {
          icon    : icon_vue,
          label   : 'VueJs',
          amount  : 80,
        },

        {
          icon    : icon_xd,
          label   : 'Adobe Xd',
          amount  : 100,
        },


      ],
    }
  }
}
</script>

<style scoped lang="scss">
  #skill-rates{
    padding-top: 100px;
    padding-bottom: 100px;
    background-color: var(--color-primary);
    position: relative;
    .icon-background{
      position: absolute;
      left: 0;
      top: 0;
      bottom: 0;
      right: 0;
      opacity: .09;
      background-size: 40%;
    }
  }

  .rate-cols {
    display: grid;
    //grid-template-columns: 400px auto;
    align-items: center;
    gap: 25px;
    position: relative;
  }

  .rate-col-left {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 10px;
    direction: ltr;
  }

  .rate-col-right{
    svg {
      max-width: 100%;
      height: auto;
      margin: 50px auto;
      display: block;
      transform: rotate(-90deg);
      width: 200px;
    }
    h2 {
      text-align: center;
      font-size: 42px;
      font-weight: bold;
      color: #FFF;
      margin-bottom: 20px;
    }
  }

  .rate {
    background: #FFF;
    padding: 10px;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    strong {
      font-size: 18px;
      font-weight: 500;
    }
    img {
      height: 64px;
    }
    .amount {
      background: #cfcfcf;
      height: 7px;
      width: 100%;
      border-radius: 8px;
      position: relative;
      div {
        position: absolute;
        left: 0;
        top: 0;
        bottom: 0;
        border-radius: 8px;
        background: var(--color-primary);
        width: 15%;
      }
    }
  }

  @media screen and ( min-width: 600px ){
    .rate-col-left {
      grid-template-columns: repeat(3, 1fr);
    }
  }

  @media screen and ( min-width: 768px ){
    .rate-col-left {
      grid-template-columns: repeat(4, 1fr);
    }
  }

  @media screen and ( min-width: 992px ){
    .rate-col-left {
      grid-template-columns: repeat(5, 1fr);
    }
  }

  @media screen and ( min-width: 1200px ){
    .rate-col-right{
      svg{
        transform: none;
      }
    }
    .rate-cols{
      grid-template-columns: 300px auto;
    }
    .rate-col-left {
      //grid-template-columns: repeat(4, 1fr);
    }
  }

</style>