<template>
  <div>
    <nav class="py-4">
      <div class="max-w-7xl mx-auto px-8">
        <div class="flex items-center justify-between h-16">
          <div class="flex items-center">
            <Logo />
            <div class="hidden md:block">
              <div class="ml-10 flex items-baseline space-x-4">
                <a
                  v-for="option in headerOptions"
                  :key="option"
                  class="
                    text-gray-300
                    hover:border-white
                    border border-transparent
                    px-3
                    py-2
                    rounded-md
                    text-sm
                    font-medium
                  "
                  :class="{ 'bg-white text-gray-800': option == '/' }"
                  :href="option"
                  >{{ option == '/' ? 'Home' : option }}</a
                >
              </div>
            </div>
          </div>
          <div class="block">
            <div class="ml-4 flex items-center md:ml-6"></div>
          </div>
          <div class="-mr-2 flex md:hidden">
            <button
              class="
                text-white
                hover:bg-white hover:text-gray-300
                inline-flex
                items-center
                justify-center
                p-2
                rounded-md
                focus:outline-none
              "
              @click="toggleHeadbar"
            >
              <svg
                width="20"
                height="20"
                fill="currentColor"
                class="h-8 w-8"
                viewBox="0 0 1792 1792"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  d="M1664 1344v128q0 26-19 45t-45 19h-1408q-26 0-45-19t-19-45v-128q0-26 19-45t45-19h1408q26 0 45 19t19 45zm0-512v128q0 26-19 45t-45 19h-1408q-26 0-45-19t-19-45v-128q0-26 19-45t45-19h1408q26 0 45 19t19 45zm0-512v128q0 26-19 45t-45 19h-1408q-26 0-45-19t-19-45v-128q0-26 19-45t45-19h1408q26 0 45 19t19 45z"
                ></path>
              </svg>
            </button>
          </div>
        </div>
      </div>
      <div class="md:hidden" :class="{ hidden: !headbarActive }">
        <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
          <a
            v-for="option in headerOptions"
            :key="option"
            :href="option"
            class="
              text-gray-300
              border border-transparent
              hover:border-white
              block
              px-3
              py-2
              rounded-md
              text-base
              font-medium
            "
            :class="{ 'text-gray-800 bg-white': option == '/' }"
            >{{ option == '/' ? 'Home' : option }}</a
          >
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  data() {
    return {
      headbarActive: false,
      headerOptions: [
        '/',
        'Articles',
        'Lessons',
        'Courses',
        'Pricing',
        'Sponsor',
      ],
    }
  },
  methods: {
    toggleHeadbar() {
      this.headbarActive = !this.headbarActive
    },
  },
}
</script>
