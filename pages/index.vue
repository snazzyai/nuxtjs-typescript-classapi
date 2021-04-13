<template>
  <div class="container">
      <h1 class="title">
        Simple Counter
      </h1>
      <div class="btn-container">
        <Button @counter-change="decrement" buttonText="-" />
        <p>Counter: {{counter}}</p>
        <Button @counter-change="increment" buttonText="+"  />
      </div>
  </div>
</template>

<script lang="ts">
import {Vue, Component, Prop, Emit} from 'vue-property-decorator'

@Component
export default class Counter extends Vue {
  counter: number = 0

  @Emit()
  increment():void{
    this.counter++
  }

  @Emit()
  decrement():void{
    this.counter--
  }

}

</script>

<style lang="scss">
.container{
  text-align: center;
  background: #da9a99;

}
.btn-container{
  display: flex;
  flex-direction: row;
  justify-content: center;
  padding: 3rem;
  p {
    color: #fff;
    font-size: 2rem;
  }
}
.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

</style>
