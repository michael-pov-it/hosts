<template>
  <div class="hosts">
    <HelloWorld msg="Welcome to Hosts page" />
    <div id="hosts-list" v-for="hosts in data" :key="hosts.machines">
      <h2>Categories</h2>
      <div class="categories">
        <div
          v-for="(index, category) in hosts.telvent"
          :key="category.vsphere"
          class="category">
          <h3>{{ category }}</h3>
          <div v-for="(value, key) in index" :key="key.value">
          {{ key }}: {{ value }}
          </div>
        </div>
      </div>
    </div>
    <Bottom />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue"
import Bottom from "@/components/Bottom.vue"

import data from '@/assets/json/data.json'

let testStr = "http://telvent.web-dev-studio.com/json/data.json"
fetch(testStr).then(r=>( console.log(r.json) ))

export default {
  name: "Home",
  components: {
    HelloWorld,
    Bottom
  },
  el() {
    `#hosts-list`
  },
  data() {
    return {
      data: data
    }
  }
}
</script>
<style lang="css">
  .category {
    text-align: left;
    float: left;
  }
  .categories {
    display: flex;
    padding: 0 5% 30px;
    justify-content: space-between;
  }
</style>