<template>
  <div ref="container">
    <h2>Hello {{ blockf }}</h2>
    <button ref="blocks" @click="blockElement()">Block</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    block: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      blockf: this.block
    }
  },
  mounted() {
    if (this.blockf) {
      this.$refs.container.classList.add('fix');
    }
  },
  methods: {
    blockElement () {
      if (this.blockf) {
        this.blockf=false;
        this.$refs.blocks.innerText="Block"
        this.$refs.container.classList.remove('fix');
      } else {
        this.blockf=true;
        this.$refs.blocks.innerText="Unblock"
        this.$refs.container.classList.add('fix');
      }
    }
  }
}
</script>

<style scoped>
  div {
    width: 300px;
    height: 100px;
    background-color: orange;
    text-align: center;
    vertical-align: middle;
  }

  div.fix {
    background-color: var(--theme-color);
  }
</style>
