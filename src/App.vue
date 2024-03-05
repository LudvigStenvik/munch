<template>
  <div id="app">
    <Index />
  </div>
</template>

<script>
import Index from './pages/Index.vue';
import SelfieCapture from "@/components/SelfieCapture.vue";

export default {
  name: 'App',
  components: {
    SelfieCapture,
    Index,
  }
};
</script>

<style>
/* Global styles */
body, html {
  margin: 0;
  padding: 0;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background: #ecf0f1;
  box-sizing: border-box;
}

#app {
  display: flex;
  padding: 0;
  margin: 0;
  flex-direction: column;
  align-items: center;
  min-height: 100vh;
  min-width: 100vw;
  justify-content: center;
}

.header {
  background-color: #000000;
  color: white;
  padding: 2vw;
  margin: 0;
  text-align: center;
  font-family: Impact,Haettenschweiler,Franklin Gothic Bold,Charcoal,Helvetica Inserat,Bitstream Vera Sans Bold,Arial Black,sans serif;
  width: 100vw;
}
h1 {
  font-size: 60px;
  font-weight: 600;
  color: #fbfbfb
}

.selfie-capture {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  max-width: 600px;
  margin: 0 auto;
  padding: 0;
}

.selfie-capture button{
  align-items: center;
  appearance: none;
  background-color: #fff;
  border-radius: 24px;
  border-style: none;
  box-shadow: rgba(0, 0, 0, .2) 0 3px 5px -1px,rgba(0, 0, 0, .14) 0 6px 10px 0,rgba(0, 0, 0, .12) 0 1px 18px 0;
  box-sizing: border-box;
  color: #3c4043;
  cursor: pointer;
  display: inline-flex;
  fill: currentcolor;
  font-family: Impact,Haettenschweiler,Franklin Gothic Bold,Charcoal,Helvetica Inserat,Bitstream Vera Sans Bold,Arial Black,sans serif;
  font-size: 34px;
  font-weight: 500;
  height: 60px;
  justify-content: center;
  letter-spacing: .25px;
  line-height: normal;
  max-width: 100%;
  overflow: visible;
  padding: 2px 44px;
  position: relative;
  text-align: center;
  text-transform: none;
  transition: box-shadow 280ms cubic-bezier(.4, 0, .2, 1),opacity 15ms linear 30ms,transform 270ms cubic-bezier(0, 0, .2, 1) 0ms;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  width: auto;
  will-change: transform,opacity;
  z-index: 0;
}

.selfie-capture button:hover {
  background: #F6F9FE;
  color: #FE390F;
}

</style>
