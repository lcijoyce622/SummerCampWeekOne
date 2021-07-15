<template>
  <div class="cardpool" v-for="item in results" :key="item.id.value">
    <div class="card">
      <div class="img">
        <img :src="item.picture.large" alt="item.name.title" />
      </div>
      <div class="card_content">
        <h3 :class="item.gender === 'male' ? 'male' : 'female'">
          {{ item.name.title }}{{ item.name.first }}{{ item.name.last }}
        </h3>
        <p>
          Email：<a href="mailto:{{item.email}}">{{ item.email }}</a>
        </p>
        <p>
          Phone：<a href="tel:{{item.phone}}">{{ item.phone }}</a>
        </p>
        <p>
          Address：<a
            :href="
              'https://www.google.com.tw/maps/search/' +
              item.location.city +
              item.location.state
            "
            target="_blank"
          >
            {{ item.location.city }} {{ item.location.state }}
            {{ item.location.country }} {{ item.location.postcode }}
          </a>
        </p>
      </div>
      <div class="map">
        <iframe
          width="100%"
          height="100%"
          frameborder="0"
          scrolling="no"
          marginheight="0"
          marginwidth="0"
          :src="
            'https://maps.google.com.tw/maps?f=q&amp;hl=zh-TW&amp;geocode=&amp;q=' +
            parseInt(item.location.coordinates.latitude) +
            ',' +
            parseInt(item.location.coordinates.longitude) +
            '&amp;z=10&amp;output=embed'
          "
        ></iframe>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["results"],
  
};
</script>

<style lang="scss" scoped>

  .cardpool {
    .card:hover {
      background-color: rgb(221, 244, 255);
      box-shadow:  0 0.25rem 0.75rem rgba(94, 93, 93, 0.438);
      border: 2px solid rgb(134, 134, 134);
    }
    .card {
      padding: 20px;
      margin: 1rem auto;
      width: 55%;
      display: grid;
      border: 2px solid rgb(187, 186, 186);
      border-radius: 20px;
      .img {
        width:50%;
        margin: auto;
        img {
          border-radius:50%;
          height: auto;
          width: 100%;
        }
      }

      .card_content {
        // width: 60%;
        text-align: start;
        margin: auto;
        a {
          color: black;
        }
        .male {
          color: rgb(95, 95, 187);
        }
        .female {
          color: rgb(253, 113, 136);
        }
        h3 {
          text-align: center;
        }
      }
      .map {
        // width: 20%;
        iframe {
          width: 100%;
          border: 1px solid rgb(187, 186, 186);
          border-radius: 20px;
        }
      }
    }
    @media (min-width: 992px) {
      .card {
        grid-auto-flow: column;
        grid-template-columns: 30% 40% 30%;
        justify-content: space-between;
        //  place-items:center;
        .card_content {
          margin: 0;
          padding: 0;
          h3 {
            text-align: start;
          }
        }
      }
    }
  }
</style>