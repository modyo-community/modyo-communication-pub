<template>
  <div>
    <h2>
      Pub
    </h2>
    <p>Click a card to send</p>
    <div>
      <button @click="send(1)">
        Card 1
      </button>
      <button @click="send(2)">
        Card 2
      </button>
      <button @click="send(3)">
        Card 3
      </button>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      observable: null,
      channel: 'cardIndex',
    };
  },
  methods: {
    send(item) {
      const newData = {
        item,
        saludo() {
          return 'hello';
        },
        prop: 'prop A',
      };
      window.mitt.emit(this.channel, newData);
    },
  },
};
</script>

<style lang="scss" scoped>
</style>
