<template>
  <a class="course" :href="course.url">
    <picture>
      <img :src="course.thumbnail" :alt="course.title" width="1920" height="1098" loading="lazy">
    </picture>
    <h3>{{course.title}}</h3>

    <div class="card-row">
      <p class="card-blog-author">
        <svg xmlns="http://www.w3.org/2000/svg" width="19.67" height="21.58" viewBox="0 0 19.67 21.58">
          <g id="user-octagon" transform="translate(-2.16 -1.21)">
            <path id="Path_2" data-name="Path 2" d="M21.08,8.58v6.84a3.174,3.174,0,0,1-1.57,2.73l-5.94,3.43a3.163,3.163,0,0,1-3.15,0L4.48,18.15a3.149,3.149,0,0,1-1.57-2.73V8.58A3.174,3.174,0,0,1,4.48,5.85l5.94-3.43a3.163,3.163,0,0,1,3.15,0l5.94,3.43A3.162,3.162,0,0,1,21.08,8.58Z" fill="none" stroke="#292d32" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5"></path>
            <path id="Path_3" data-name="Path 3" d="M12,11A2.33,2.33,0,1,0,9.67,8.67,2.33,2.33,0,0,0,12,11Z" fill="none" stroke="#292d32" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5"></path>
            <path id="Path_4" data-name="Path 4" d="M16,16.66c0-1.8-1.79-3.26-4-3.26s-4,1.46-4,3.26" fill="none" stroke="#292d32" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5"></path>
          </g>
        </svg>
        {{course.teacher.first_name}} {{course.teacher.last_name}}
      </p>
      <p class="card-course-old-price">
        <template v-if="course.price > course.sale_price">
          <del>{{tooman(course.price)}}</del>
          <span>{{discount_percent}}%</span>
        </template>
      </p>
    </div>

    <div class="card-row">
      <p class="card-course-duration">
        <svg xmlns="http://www.w3.org/2000/svg" width="19" height="21.5" viewBox="0 0 19 21.5">
          <g id="timer-start" transform="translate(-2.5 -1.25)">
            <path id="Path_5" data-name="Path 5" d="M12,8v5" fill="none" stroke="#292d32" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5"></path>
            <path id="Path_6" data-name="Path 6" d="M12,22a8.75,8.75,0,1,1,8.75-8.75" fill="none" stroke="#292d32" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5"></path>
            <path id="Path_7" data-name="Path 7" d="M9,2h6" fill="none" stroke="#292d32" stroke-linecap="round" stroke-linejoin="round" stroke-miterlimit="10" stroke-width="1.5"></path>
            <path id="Path_8" data-name="Path 8" d="M14.9,18.5V17.34c0-1.43,1.02-2.02,2.26-1.3l1,.58,1,.58a1.381,1.381,0,0,1,0,2.61l-1,.58-1,.58c-1.24.72-2.26.13-2.26-1.3Z" fill="none" stroke="#292d32" stroke-linecap="round" stroke-linejoin="round" stroke-miterlimit="10" stroke-width="1.5"></path>
          </g>
        </svg>
        {{course.duration_format}}
      </p>
      <p class="card-course-price">
        <template v-if="course.sale_price">
          <ins>{{tooman(course.sale_price) }}</ins>
          <span>تومان</span>
        </template>
        <template v-else>
          <ins>رایگان</ins>
        </template>
      </p>
    </div>

    <footer>
      <div class="rates"></div>
      <span class="btn btn-primary">مشاهده دوره</span>
    </footer>
  </a>
</template>

<script>
export default {
  name  : "CourseCard",
  props :{
    course  : {
      type: Object
    }
  },
  methods: {
    tooman( price ){
      let tooman = parseInt( price ) / 10;
      tooman = tooman + '';
      return tooman.replace(/\B(?=(\d{3})+(?!\d))/g, ",");
    }
  },
  computed:{
    discount_percent(){
      return Math.round( ( this.course.price - this.course.sale_price ) / this.course.price * 100 );
    }
  }
}
</script>

<style scoped lang="scss">
  .course{
    margin-top: 60px;
    background: #FFF;
    border-radius: 20px;
    padding: 12px;
    box-shadow: 0 3px 6px rgba(0, 0, 0, .16);
    transition: 0.2s;
    &:hover {
      transform: scale(1.05);
    }
    picture {
      margin: -12px -12px 0 -12px;
      display: block;
      img {
        border-radius: 20px;
        max-width: calc(100% - 23px);
        height: auto;
        display: block;
        margin: -60px auto 10px;
        box-shadow: 0 3px 6px rgba(0, 0, 0, .16);
      }
    }
    h3 {
      font-size: 18px;
      font-weight: 550;
      height: 60px;
      overflow: hidden;
    }
    .card-row {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin: 15px 0;
      p {
        display: flex;
        align-items: center;
        gap: 3px;
      }
    }
    footer{
      display: flex;
      align-items: center;
      justify-content: space-between;
      border-top: 1px dashed #E6E6E6;
      padding-top: 10px;
    }
  }

  .card-blog-author {
    color: var(--color-primary);
  }

  .card-course-old-price {
    span {
      background: var(--color-error);
      color: #FFF;
      padding: 0 3px;
      border-radius: 6px;
    }
    del {
      text-decoration: none;
      color: var(--color-error);
      position: relative;
      margin-left: 4px;
      &:before {
        content: "";
        background: red;
        height: 1px;
        left: 0;
        right: 0;
        position: absolute;
        top: 40%;
        transform: rotate(-18deg);
      }
    }
  }

  .card-course-price{
    ins {
      color: var(--color-success);
      text-decoration: none;
      font-size: 20px;
      font-weight: 600;
    }
    span {
      color: var(--color-success);
      font-size: 14px;
    }
  }
</style>