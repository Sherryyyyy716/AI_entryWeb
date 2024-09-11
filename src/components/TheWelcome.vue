<script setup>
import WelcomeItem from './WelcomeItem.vue'
import Footer from '@/components/FooterItem.vue'
import Form from '@/components/FormItem.vue'
import DKFooter from '@/components/DKFooter.vue'
import { config } from '@/composables/config'

const { projectList } = config




// import DocumentationIcon from './icons/IconDocumentation.vue'
// import ToolingIcon from './icons/IconTooling.vue'
// import EcosystemIcon from './icons/IconEcosystem.vue'
// import CommunityIcon from './icons/IconCommunity.vue'
// import SupportIcon from './icons/IconSupport.vue'
</script>

<template>
  <div class="h-screen">
    <div
      class="bg-white  border border-solid border-sky-600 h-20 !py-0 px-6 justify-center flex-shrink-0 items-center"
    >
      <div class="flex items-center justify-between h-full">
        <img src="https://static.wixstatic.com/media/fb8d75_f5377228c19347b4b3dc5a665b4a91c1~mv2.png/v1/fill/w_148,h_38,al_c,q_85,usm_0.66_1.00_0.01,enc_auto/DexatekLogo(O).png" alt="Logo" class="w-28" />
        <h2 class="pl-4 text-green">Welcome</h2>
      </div>
    </div>
    <div class="w-full bg-slate-300 h-80 flex justify-center"> <div class="m-auto w-fit ">banner</div></div>
    <div class="mx-auto  w-full  pt-10 pb-20    bg-white" >
        <h2 class="text-3xl text-center text-[#0A2F5A] font-medium mb-8">智慧問答1</h2>
      <div class="flex sm:justify-around lg:justify-between sm:w-4/5 w-11/12 lg:w-[960px] mx-auto flex-wrap gap-x-1 gap-y-4">
        <WelcomeItem class="lg:w-[32%] sm:w-[48%] sm:h-[250px]" v-for="(item, index) in projectList" :key="index">
          <p class="mb-2 mx-auto w-fit lg:w-auto w-max-[300px]">
            {{item.Introduction}}
          </p>

          <template #heading>{{item.name}}</template>
          <template #btn>Try me!</template>
        </WelcomeItem>
      </div>
    </div>
       <div class="px-6 my-10 py-0  mx-auto lg:w-[960px] h-[2px] rounded w-10/12"  style="background:radial-gradient(circle, rgb(101 125 147 / 77%)  0%, rgb(62 132 186 / 9%) 100%);"></div>
       <div class="mx-auto  w-full  pt-10 pb-20    bg-white" >
        <h2 class="text-3xl text-center text-[#0A2F5A] font-medium mb-8">專案介紹2</h2>
      <div class="flex sm:justify-around lg:justify-between sm:w-4/5 w-11/12 lg:w-[960px] mx-auto flex-wrap gap-x-1 gap-y-4">
        <WelcomeItem class="lg:w-[32%] sm:w-[48%] sm:h-[250px]" v-for="(item, index) in projectList" :key="index">
          <p class="mb-2 mx-auto w-fit lg:w-auto w-max-[300px]">
            {{item.Introduction}}
          </p>

          <template #heading>{{item.name}}</template>
          <template #btn>Try me!</template>
        </WelcomeItem>
      </div>
    </div> 
   

    <div class="  mx-auto my-20 ">
      <Footer class="w-11/12 mx-auto lg:w-[960px]">
        <template #heading>我要找客製化AI工具！</template>
        <p class="mb-2 mx-auto w-full  lg:w-auto ">
          <Form  class="w-full mx-auto">
            <template #service>
           
            </template>
          </Form>
        </p>
        <template #btn> <div class="text-xl">申請</div></template>
      </Footer>
    </div>
    <DKFooter/>
  </div>
  

  <!-- 
  <WelcomeItem>
    <template #icon>
      <ToolingIcon />
    </template>
    <template #heading>Tooling</template>

    This project is served and bundled with
    <a href="https://vitejs.dev/guide/features.html" target="_blank" rel="noopener">Vite</a>. The
    recommended IDE setup is
    <a href="https://code.visualstudio.com/" target="_blank" rel="noopener">VSCode</a> +
    <a href="https://github.com/johnsoncodehk/volar" target="_blank" rel="noopener">Volar</a>. If
    you need to test your components and web pages, check out
    <a href="https://www.cypress.io/" target="_blank" rel="noopener">Cypress</a> and
    <a href="https://on.cypress.io/component" target="_blank" rel="noopener"
      >Cypress Component Testing</a
    >.

    <br />

    More instructions are available in <code>README.md</code>.
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <EcosystemIcon />
    </template>
    <template #heading>Ecosystem</template>

    Get official tools and libraries for your project:
    <a href="https://pinia.vuejs.org/" target="_blank" rel="noopener">Pinia</a>,
    <a href="https://router.vuejs.org/" target="_blank" rel="noopener">Vue Router</a>,
    <a href="https://test-utils.vuejs.org/" target="_blank" rel="noopener">Vue Test Utils</a>, and
    <a href="https://github.com/vuejs/devtools" target="_blank" rel="noopener">Vue Dev Tools</a>. If
    you need more resources, we suggest paying
    <a href="https://github.com/vuejs/awesome-vue" target="_blank" rel="noopener">Awesome Vue</a>
    a visit.
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <CommunityIcon />
    </template>
    <template #heading>Community</template>

    Got stuck? Ask your question on
    <a href="https://chat.vuejs.org" target="_blank" rel="noopener">Vue Land</a>, our official
    Discord server, or
    <a href="https://stackoverflow.com/questions/tagged/vue.js" target="_blank" rel="noopener"
      >StackOverflow</a
    >. You should also subscribe to
    <a href="https://news.vuejs.org" target="_blank" rel="noopener">our mailing list</a> and follow
    the official
    <a href="https://twitter.com/vuejs" target="_blank" rel="noopener">@vuejs</a>
    twitter account for latest news in the Vue world.
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <SupportIcon />
    </template>
    <template #heading>Support Vue</template>

    As an independent project, Vue relies on community backing for its sustainability. You can help
    us by
    <a href="https://vuejs.org/sponsor/" target="_blank" rel="noopener">becoming a sponsor</a>.
  </WelcomeItem> -->
</template>
