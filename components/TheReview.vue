<template>
  <section
    class="module module--reviews"
    :class="color == 'light' ? 'sm:bg-white' : 'bg-gray-900'"
  >
    <div class="container">
      <div
        class="
          flex flex-col
          justify-center
          items-center
          sm:flex-row sm:justify-between
        "
      >
        <div
          v-for="(review, index) in reviews"
          :key="index"
          :class="index == 0 ? 'mt-0' : 'mt-8 sm:mt-0'"
        >
          <a :href="review.link" class="block" target="_blank">
            <img
              :src="
                '/images/' +
                review.logo +
                '-' +
                (color == 'light' ? 'dark' : 'light') +
                '.svg'
              "
              class="h-16 sm:h-14 lg:h-20"
            />
          </a>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  props: {
    color: {
      default: "dark",
      type: String
    }
  },
  data() {
    return {
      reviews: [
        {
          logo: "capterra-review",
          link: "https://www.capterra.com/p/189116/WhatsHash/reviews/"
        },
        {
          logo: "appsumo-review",
          link: "https://appsumo.com/products/vepaar/"
        },
        {
          logo: "trustpilot-review",
          link: "https://www.trustpilot.com/review/vepaar.com"
        }
      ]
    };
  }
};
</script>