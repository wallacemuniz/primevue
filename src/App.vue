<template>
  <div id="app">
    <div class="app-container">
      <img alt="Vue logo" src="./assets/primevue-logo.png">
      <HelloWorld msg="Welcome to Your PrimeVue App"/>
      <form @submit.prevent="greet">
        <InputText type="text" v-model="text"/>
        <Button type="submit" label="Submit"/>
        <h3>{{message}}</h3>
      </form>
    </div>

    <Toast/>
  </div>
  <div>
    <Accordion>
      <AccordionTab header="Header I - i">
        Content
      </AccordionTab>
      <AccordionTab header="Header II - ii">
        Content 2
      </AccordionTab>
      <AccordionTab header="Header III - iii">
        Content 3
      </AccordionTab>
    </Accordion>
  </div>
</template>

<script>
  /* import Accordion from 'primevue/accordion';
  import AccordionTab from 'primevue/accordiontab'; */

  import HelloWorld from './components/HelloWorld.vue'

  export default {
      data() {
          return {
              message: null,
              text: null
          }
      },
      methods: {
          greet() {
              this.$toast.add({severity: 'info', summary: 'Hello '  + this.text});
              this.message = 'Hello ' + this.text;
          }
      },
      components: {
        HelloWorld
      }
  }
</script>

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

.app-container {
  text-align: center;
}

body #app .p-button {
  margin-left: .2em;
}

form {
  margin-top: 2em;
}
</style>