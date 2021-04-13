<template>
  <div class="container">
    <button class="btn" @click="changeCounter">{{buttonText}}</button>
  </div>
</template>
<script lang="ts">
import {Vue, Prop, Component, Emit} from 'vue-property-decorator'

@Component
export default class Button extends Vue {
  @Prop()
  buttonText!: string;

  @Emit()
  changeCounter():void{
    this.$emit('counter-change')
  }
}
</script>
<style scoped>
  .btn {
    color: green;
    background: #fff;
    margin: .5rem 2rem

  }
</style>
