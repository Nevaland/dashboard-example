<template>
  <div class="home">
    <div class="ma-5 secondary text-no-wrap rounded-lg">
      <v-app-bar color="grey darken-3" dark class="rounded-lg">
        <v-text-field label="Search" prepend-icon="mdi-magnify" color="white">
        </v-text-field>
        <v-spacer></v-spacer>
        <v-btn icon> <v-icon>mdi-bell</v-icon></v-btn>
        <v-avatar>
          <img src="https://cdn.vuetifyjs.com/images/john.jpg" alt="john" />
        </v-avatar>
      </v-app-bar>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    arrayEvents: null,
    date2: new Date().toISOString().substr(0, 10),
    selected: [2],
    selected1: [1],
    items: [
      {
        title: "01 Create wireframe",
      },
      {
        title: "02 Slack Logo Design",
      },
      {
        title: "03 Dashboard Design",
      },
      {
        title: "04 Create wireframe",
      },
    ],
    articles: [
      {
        title: "01 Create wireframe",
      },
      {
        title: "02 Slack Logo Design",
      },
    ],
    recent: [
      {
        active: true,
        avatar: "https://cdn.vuetifyjs.com/images/lists/1.jpg",
        title: "Jason Oner",
      },
      {
        active: true,
        avatar: "https://cdn.vuetifyjs.com/images/lists/2.jpg",
        title: "Mike Carlson",
      },
      {
        avatar: "https://cdn.vuetifyjs.com/images/lists/3.jpg",
        title: "Cindy Baker",
      },
      {
        avatar: "https://cdn.vuetifyjs.com/images/lists/4.jpg",
        title: "Ali Connors",
      },
    ],
  }),
  mounted() {
    this.arrayEvents = [...Array(6)].map(() => {
      const day = Math.floor(Math.random() * 30);
      const d = new Date();
      d.setDate(day);
      return d.toISOString().substr(0, 10);
    });
  },
  method: {
    functionEvents(date) {
      const [, , day] = date.split("-");
      if ([12, 17, 28].includes(parseInt(day, 10))) return true;
      if ([1, 19, 22].includes(parseInt(day, 10))) return ["red", "#00f"];
      return false;
    },
  },
};
</script>
