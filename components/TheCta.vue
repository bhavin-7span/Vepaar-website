<template>
  <section class="module module--cta">
    <div class="container">
      <div class="lg:flex items-end">
        <div class="flex-1 sm:pr-5">
          <p class="text-lg text-white">{{ tagline }}</p>
          <h2
            class="text-3xl lg:text-5xl text-white font-semibold my-5 max-w-lg"
          >
            {{ title }}
          </h2>
          <p class="text-base font-light sm:font-normal sm:text-lg text-white">
            {{ description }}
          </p>
        </div>
        <div class="w-64 lg:max-w-xs mt-5">
          <the-button
            v-if="getStarted"
            href="#whatsapp-link"
            color="white"
            class="w-full justify-center"
            >Get Started Now!</the-button
          >
          <div v-else>
            <div class="flex items-center lg:justify-end mb-2">
              <label class="block text-white">Available On:</label>
              <div class="flex">
                <a
                  :href="link.href"
                  v-for="(link, index) in downloadLinks"
                  :key="index"
                  class="w-8 h-8 flex items-center justify-center"
                >
                  <img
                    :src="'/images/' + link.icon"
                    alt=""
                    class="object-contain object-center"
                  />
                </a>
              </div>
            </div>
            <the-button
              color="white"
              class="w-full justify-center"
              href="https://web.vepaar.com/#/signup"
              >Sign Up for Free!</the-button
            >
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  props: {
    tagline: String,
    title: String,
    description: String,
    getStarted: {
      default: false,
      type: Boolean
    }
  },
  data() {
    return {
      downloadLinks: [
        {
          icon: "web.svg",
          href:
            "https://chrome.google.com/webstore/detail/vepaar-crm-for-whatsapp/bkokmlhcdmoeobdcabifliikflimplol"
        },
        {
          icon: "iOS.svg",
          href:
            "https://apps.apple.com/gb/app/whatshash-product-catalog/id1477039888"
        },
        {
          icon: "android.svg",
          href:
            "https://play.google.com/store/apps/details?id=com.whatshash&hl=en_CA"
        }
      ]
    };
  }
};
</script>
<style lang="scss">
.module--cta {
  background-image: url("/images/cta-business-bg.jpg");
  @apply bg-cover bg-center py-12 sm:py-28;
}
</style>