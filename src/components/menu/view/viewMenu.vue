<template>
<div class="menu-container">
  <mold :default-mold="defaultMold" @moldChange="handleMoldChange"/>
<!--  <theme/>-->
  <arrange/>
  <styleOperation/>
  <fontOperation/>
</div>

</template>

<script>
import mold from './mold'
import theme from './theme'
import arrange from './arrange'
import styleOperation from './styleOperation'
import fontOperation from './fontOperation.vue'
import {moleProps} from "../../props";

export default {
  name: 'viewMenu',
  components: {
    mold,
    theme,
    arrange,
    styleOperation,
    fontOperation
  },
  props: {
    ...moleProps,
    minder: {}
  },
  methods: {
    handleMoldChange(data) {
      this.$emit('moldChange', data);
    }
  }
}

</script>

<style scoped>
  .menu-container >>> i {
    display: inline-block;
    width: 20px;
    height: 20px;
  }
</style>
