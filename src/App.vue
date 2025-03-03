<template>
  <div class="bg-[#222222] min-h-screen overflow-hidden">
    <n-modal v-model:show="showModal">
      <n-card
        class="flex items-center bg-white rounded p-5 flex-col  font-mono
"
        style="width: 600px"
        title="Selector de Idioma - Language Selector"
        :bordered="true"
        size="huge"
        role="dialog"
        aria-modal="true"
      >
        <template #header-extra> </template>
        <n-alert title="Version Beta" type="warning" closable>
          Estas visualizando una version beta en la cual la parte backend no esta disponible aun, disculpa las molestias :(
        </n-alert>
        <div class="flex xl:flex-row flex-col items-center justify-center gap-10 mt-4">
          <button @click="setLang('en')">
            <div
              class="flex items-center justify-center flex-col hover:scale-110 transition cursor-pointer duration-250"
            >
              <button class="rounded bolder-dark border-solid border-2 p-2
">
                Okay!
              </button>
            </div>
          </button>
        </div>
      </n-card>
    </n-modal>
    <DefaultLayout></DefaultLayout>
    <n-message-provider>
      <div>
        <router-view></router-view>
      </div>
    </n-message-provider> 
  </div>
  <footer class="w-full h-10 bg-slate-600  border-t-2 text-white flex flex-row justify-between p-4">
        <p class="mb-2">
          Page created by Roman Myziuk 
        </p>
        <p>
          All rights reserver &copy;
        </p>
      </footer>
</template>

<script>
  import DefaultLayout from './components/DefaultLayout.vue'
  import 'vue3-loading-overlay/dist/vue3-loading-overlay.css';
  import { NMessageProvider, NModal } from 'naive-ui'
  import { ref } from 'vue'
  export default{
    setup(){
      const showModal = ref(true)
      return{
        showModal
      }
    },
    components:{
      DefaultLayout, NMessageProvider, NModal
    },
    methods:{
      setLang(lang){
      this.showModal = false
    }
    }
  }

</script>
