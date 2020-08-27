<template>
  <div class="hosts">
    <HelloWorld msg="Welcome to Hosts page" />
    <div id="hosts-list" v-for="host in this.hosts" :key="host.infrastructure">
      <h2>Inftastructure</h2>
      {{ host.infrastructure }}
      <h2>vSphere</h2>
      {{ host.vsphere }}
      <h2>Inftastructure</h2>
      {{ host.infrastructure }}
    </div>
    <Bottom />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue"
import Bottom from "@/components/Bottom.vue"
//var hosts = JSON.parse("@/assets/json/data.json")

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
      hosts: {
        "telvent" : {
          "infrastructure" : {
            "server1": "10.10.11.12",
            "server2": "13.14.15.16"
          },
          "vsphere": {
            "server11": "17.18.19.20",
            "server2222": "22.23.24.99"
          }
        }
      }
    }
  }
}
</script>
