<template>
  <div class="about">
    <HelloWorld msg="Welcome to About page" />
    <Bottom />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue"
import Bottom from "@/components/Bottom.vue"

export default {
  name: "Home",
  components: {
    HelloWorld,
    Bottom
  }
}
</script>
