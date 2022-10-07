<template>
    <div>
      <Navbar @openChat="chatAction()" />
      <Nuxt />
      <Footer />
    </div>
</template>

<script setup lang="ts">
import { onMounted } from 'vue'
function chatAction() {
  $crisp.push(["do", "chat:open"])
}
    
onMounted(() => {
  window.$crisp=[];window.CRISP_WEBSITE_ID="390c3b34-5432-4280-a15b-2530db495da2";(function(){
    let d=document;
    let s=d.createElement("script");
    s.src="https://client.crisp.chat/l.js";
    s.async=1;
    d.getElementsByTagName("head")[0].appendChild(s);
  })();            
})
</script>