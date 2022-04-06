<template>
  <b-container fluid>
    <b-row>
      <b-col
        lg="3"
        md="4"
        sm="12"
        v-for="card in cards"
        :card="card"
        :key="card.id"
      >
        <b-card title="card.name" img-src="card.img" img-alt="image" img-top>
          <b-button href="#" variant="primary">View More</b-button>
        </b-card>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "card",
  data() {
    return {
      cards: [
        {
          id: 1,
          name: "James",
          handle: "@jokerjames",
          img: "https://semantic-ui.com/images/avatar2/large/matthew.png",
          tweet: "If you don't succeed, dust yourself off and try again.",
          likes: 10,
        },
        {
          id: 2,
          name: "Fatima",
          handle: "@fantasticfatima",
          img: "https://semantic-ui.com/images/avatar2/large/molly.png",
          tweet: "Better late than never but never late is better.",
          likes: 12,
        },
        {
          id: 3,
          name: "Xin",
          handle: "@xeroxin",
          img: "https://semantic-ui.com/images/avatar2/large/elyse.png",
          tweet: "Beauty in the struggle, ugliness in the success.",
          likes: 18,
        },
      ],
    };
  },
};
</script>

<style lang="scss"></style>
