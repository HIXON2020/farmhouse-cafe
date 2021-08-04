<template>
  <div class="bg-teal-100 border-t-4 border-green-200 rounded-b text-teal-900 shadow-md mb-5">
    <a :href="'/info/' + id + '/'" class="block px-4 py-3">
      <time class="text-gray-700 text-base mb-1 block md:w-1/6">
        {{ date }}
      </time>
      <div class="md:w-11/12">{{ title }}</div>
    </a>
  </div>
</template>

<script>
// import moment from 'moment'


export default {
  name: 'LayoutInfoList',
  props: {
    title:{
      type: String,
      required: true
    },
    date: {
      type: String,
      required: true
    },
    id: {
      type: String,
      required: true
    },
  }
}
</script>