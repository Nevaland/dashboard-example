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
    <div class="mt-n3">
      <v-container>
        <v-row>
          <v-col cols="12" sm="4">
            <v-card color="grey darken-3">
              <v-app-bar flat color="rgba(0,0,0,0)">
                <v-avatar size="45" color="grey darken-2">
                  <img src="favicon.ico" />
                </v-avatar>
                <v-toolbar-title class="title white--text pl1-0 ml-2">
                  Vue
                </v-toolbar-title>
                <v-spacer></v-spacer>
                <v-btn color="whtie" outlined icon small>
                  <v-icon color="yellow" small>mdi-star</v-icon>
                </v-btn>
                <v-btn color="white" icon>
                  <v-icon>mdi-dots-vertical</v-icon>
                </v-btn>
              </v-app-bar>
              <v-app-bar flat color="rgba(0,0,0,0)">
                <v-btn color="grey darken-2" small>SELCT PROGRESS</v-btn>
                <v-spacer></v-spacer>
                <b-btn color="red" outlined small>HIGH</b-btn>
              </v-app-bar>
              <v-app-bar flat color="rgba(0,0,0,0)" class="mt-n4">
                <p>Task Done: 25/50</p>
              </v-app-bar>
              <v-app-bar flat color="rgba(0,0,0,0)" class="mt-n10">
                <v-progress-linear
                  color="red"
                  height="6"
                  value="65"
                ></v-progress-linear>
              </v-app-bar>
              <v-app-bar flat color="rgba(0,0,0,0)" class="mt-n10">
                <v-btn color="green" small class="mr-2" text click
                  >IOS APP</v-btn
                >
                <v-btn color="green" small text>UI/UX</v-btn>
              </v-app-bar>

              <v-app-bar flat color="rgba(0,0,0,0)" class="mt-n7">
                <v-avatar size="30">
                  <img
                    src="https://cdn.vuetifyjs.com/images/john.jpg"
                    alt="john"
                  />
                </v-avatar>
                <v-avatar size="30" class="ml-n3">
                  <img
                    src="https://cdn.vuetifyjs.com/images/lists/1.jpg"
                    alt="john"
                  />
                </v-avatar>
                <v-avatar size="30" class="ml-n3">
                  <img
                    src="https://cdn.vuetifyjs.com/images/lists/2.jpg"
                    alt="john"
                  />
                </v-avatar>
                <v-avatar size="30" class="ml-n3">
                  <img
                    src="https://cdn.vuetifyjs.com/images/lists/3.jpg"
                    alt="john"
                  />
                </v-avatar>
                <v-avatar size="30" class="ml-n3">
                  <img
                    src="https://cdn.vuetifyjs.com/images/lists/4.jpg"
                    alt="john"
                  />
                </v-avatar>
                <v-avatar size="30" class="ml-n3" color="grey darken-2">
                  +5
                </v-avatar>
              </v-app-bar>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
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
