<template>
  <div>
    <ClickCounter></ClickCounter>
    <HoverCounter></HoverCounter>

    <!-- <PersonApp></PersonApp> -->
    <!-- <TemplateRef></TemplateRef> -->

    <!-- <ProvideInject></ProvideInject> -->
    <!-- <WatchApp></WatchApp> -->
    <!-- <ComputedApp></ComputedApp> -->
    <!-- <VModel></VModel> -->
    <!-- <MethodsApp></MethodsApp> -->
    <!-- <DemoTwo></DemoTwo> -->
    <!-- <DataApp></DataApp> -->
  <!-- <DemoOne></DemoOne> -->
  </div>
  
</template>

<script>
// import ProvideInject from './components/ProvideInject.vue';
import ClickCounter from './components/ClickCounter.vue';
import HoverCounter from './components/HoverCounter.vue';
// import PersonApp from './components/PersonApp.vue';
// import TemplateRef from './components/TemplateRef.vue';



// import WatchApp from './components/WatchApp.vue';


// import MethodsApp from './components/MethodsApp.vue';
// import ComputedApp from './components/ComputedApp.vue';
// import VModel from './components/VModel.vue';
// import DemoOne from './components/DemoOne.vue';
// import DemoTwo from './components/DemoTwo.vue';
// import DataApp from './components/DataApp.vue';


export default {
  name: 'App',
  components: {
    // DataApp,
    // MethodsApp,
    // DemoOne,
    // DemoTwo
    // VModel,
    // ComputedApp ,
      // WatchApp,
      // ProvideInject,
      // TemplateRef
      // PersonApp

      ClickCounter,
      HoverCounter
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
