<template>
  <div class="shadow-lg rounded-2xl w-64 bg-white p-4 m-4 text-black">
    <div class="flex items-center justify-between">
      <p class="text-4xl font-medium mb-4">
        {{ planName }}
      </p>
      <p class="text-3xl font-bold flex flex-col">
        ${{ pricing }}
        <span class="font-thin text-right text-sm"> month </span>
      </p>
    </div>
    <p class="text-md mt-4">Plan include :</p>
    <ul class="text-sm w-full mt-6 mb-6">
      <li class="mb-3 flex items-center">
        <svg
          class="h-6 w-6 mr-2"
          xmlns="http://www.w3.org/2000/svg"
          width="6"
          height="6"
          stroke="currentColor"
          fill="black"
          viewBox="0 0 1792 1792"
        >
          <path
            d="M1412 734q0-28-18-46l-91-90q-19-19-45-19t-45 19l-408 407-226-226q-19-19-45-19t-45 19l-91 90q-18 18-18 46 0 27 18 45l362 362q19 19 45 19 27 0 46-19l543-543q18-18 18-45zm252 162q0 209-103 385.5t-279.5 279.5-385.5 103-385.5-103-279.5-279.5-103-385.5 103-385.5 279.5-279.5 385.5-103 385.5 103 279.5 279.5 103 385.5z"
          ></path>
        </svg>
        All illimited components
      </li>
      <li class="mb-3 flex items-center">
        <svg
          class="h-6 w-6 mr-2"
          xmlns="http://www.w3.org/2000/svg"
          width="6"
          height="6"
          stroke="currentColor"
          fill="black"
          viewBox="0 0 1792 1792"
        >
          <path
            d="M1412 734q0-28-18-46l-91-90q-19-19-45-19t-45 19l-408 407-226-226q-19-19-45-19t-45 19l-91 90q-18 18-18 46 0 27 18 45l362 362q19 19 45 19 27 0 46-19l543-543q18-18 18-45zm252 162q0 209-103 385.5t-279.5 279.5-385.5 103-385.5-103-279.5-279.5-103-385.5 103-385.5 279.5-279.5 385.5-103 385.5 103 279.5 279.5 103 385.5z"
          ></path>
        </svg>
        Own custom Tailwind styles
      </li>
      <li class="mb-3 flex items-center">
        <svg
          class="h-6 w-6 mr-2"
          xmlns="http://www.w3.org/2000/svg"
          width="6"
          height="6"
          stroke="currentColor"
          fill="black"
          viewBox="0 0 1792 1792"
        >
          <path
            d="M1412 734q0-28-18-46l-91-90q-19-19-45-19t-45 19l-408 407-226-226q-19-19-45-19t-45 19l-91 90q-18 18-18 46 0 27 18 45l362 362q19 19 45 19 27 0 46-19l543-543q18-18 18-45zm252 162q0 209-103 385.5t-279.5 279.5-385.5 103-385.5-103-279.5-279.5-103-385.5 103-385.5 279.5-279.5 385.5-103 385.5 103 279.5 279.5 103 385.5z"
          ></path>
        </svg>
        Unlimited Templates
      </li>
      <li class="mb-3 flex items-center">
        <svg
          class="h-6 w-6 mr-2"
          xmlns="http://www.w3.org/2000/svg"
          width="6"
          height="6"
          stroke="currentColor"
          fill="black"
          viewBox="0 0 1792 1792"
        >
          <path
            d="M1412 734q0-28-18-46l-91-90q-19-19-45-19t-45 19l-408 407-226-226q-19-19-45-19t-45 19l-91 90q-18 18-18 46 0 27 18 45l362 362q19 19 45 19 27 0 46-19l543-543q18-18 18-45zm252 162q0 209-103 385.5t-279.5 279.5-385.5 103-385.5-103-279.5-279.5-103-385.5 103-385.5 279.5-279.5 385.5-103 385.5 103 279.5 279.5 103 385.5z"
          ></path>
        </svg>
        Free premium dashboard
      </li>
      <li class="mb-3 flex items-center">
        <svg
          class="h-6 w-6 mr-2"
          xmlns="http://www.w3.org/2000/svg"
          width="6"
          height="6"
          stroke="currentColor"
          fill="black"
          viewBox="0 0 1792 1792"
        >
          <path
            d="M1412 734q0-28-18-46l-91-90q-19-19-45-19t-45 19l-408 407-226-226q-19-19-45-19t-45 19l-91 90q-18 18-18 46 0 27 18 45l362 362q19 19 45 19 27 0 46-19l543-543q18-18 18-45zm252 162q0 209-103 385.5t-279.5 279.5-385.5 103-385.5-103-279.5-279.5-103-385.5 103-385.5 279.5-279.5 385.5-103 385.5 103 279.5 279.5 103 385.5z"
          ></path>
        </svg>
        Best ranking
      </li>
      <li class="mb-3 flex items-center opacity-50">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="6"
          height="6"
          class="h-6 w-6 mr-2"
          fill="black"
          viewBox="0 0 1792 1792"
        >
          <path
            d="M1277 1122q0-26-19-45l-181-181 181-181q19-19 19-45 0-27-19-46l-90-90q-19-19-46-19-26 0-45 19l-181 181-181-181q-19-19-45-19-27 0-46 19l-90 90q-19 19-19 46 0 26 19 45l181 181-181 181q-19 19-19 45 0 27 19 46l90 90q19 19 46 19 26 0 45-19l181-181 181 181q19 19 45 19 27 0 46-19l90-90q19-19 19-46zm387-226q0 209-103 385.5t-279.5 279.5-385.5 103-385.5-103-279.5-279.5-103-385.5 103-385.5 279.5-279.5 385.5-103 385.5 103 279.5 279.5 103 385.5z"
          ></path>
        </svg>
        Prenium svg
      </li>
      <li class="mb-3 flex items-center opacity-50">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="6"
          height="6"
          class="h-6 w-6 mr-2"
          fill="black"
          viewBox="0 0 1792 1792"
        >
          <path
            d="M1277 1122q0-26-19-45l-181-181 181-181q19-19 19-45 0-27-19-46l-90-90q-19-19-46-19-26 0-45 19l-181 181-181-181q-19-19-45-19-27 0-46 19l-90 90q-19 19-19 46 0 26 19 45l181 181-181 181q-19 19-19 45 0 27 19 46l90 90q19 19 46 19 26 0 45-19l181-181 181 181q19 19 45 19 27 0 46-19l90-90q19-19 19-46zm387-226q0 209-103 385.5t-279.5 279.5-385.5 103-385.5-103-279.5-279.5-103-385.5 103-385.5 279.5-279.5 385.5-103 385.5 103 279.5 279.5 103 385.5z"
          ></path>
        </svg>
        My wife
      </li>
    </ul>
    <button
      type="button"
      class="
        w-full
        px-3
        py-3
        text-sm
        shadow
        rounded-lg
        text-white
        bg-black
        hover:bg-gray-500
      "
    >
      Choose plan
    </button>
  </div>
</template>

<script>
export default {
  props: ['planName', 'pricing'],
  
}
</script>

<style scoped>

</style>
