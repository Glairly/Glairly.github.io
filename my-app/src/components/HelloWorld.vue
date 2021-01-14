<template>
  <v-container fluid>
    <v-row align="center">
      <v-col cols="5">
        <v-scroll-y-transition>
          <v-card
            v-show="show.hello"
            class="ma-5"
            color="rgb(255, 255, 255, 0)"
            elevation="0"
          >
            <v-card-title class="px-0" primary-title>
              <h1 class="bigFirst">
                <span class="theme-text">Hello</span> There.
              </h1>
            </v-card-title>
            <v-card-title primary-title>
              <h2>
                My name is
                <span class="mx-2" style="color: #5353cb; font-size:1.5em;">
                  OAK
                </span>
              </h2>
            </v-card-title>
          </v-card>
        </v-scroll-y-transition>
        <v-scroll-x-transition>
          <v-card
            v-show="show.profile"
            class="theme-elevation pa-5 mt-10 text-left rounded-xl"
          >
            <v-card-title primary-title>
              <h2 class="theme-text">Profile</h2>
            </v-card-title>
            <hr />
            <v-card-text class="text-md-body-1">
              <table>
                <template v-for="(i, index) in profile">
                  <tr :key="index">
                    <th class="black--text">
                      {{ i.label }}
                    </th>

                    <th>
                      {{ i.data }}
                    </th>
                  </tr>
                </template>
              </table>
            </v-card-text>

            <v-card-title primary-title>
              <h3>Social Media</h3>
            </v-card-title>
            <v-card-text>
              <template v-for="(i, index) in social">
                <v-btn
                  class="mx-3"
                  :href="i.url"
                  :color="i.color"
                  :key="index"
                  icon
                >
                  <v-icon class="text-h3">{{ i.icon }}</v-icon>
                </v-btn>
              </template>
              <v-btn class="mx-3" href="https://line.me/ti/p/~oakfap" icon>
                <v-img width="42" src="@/assets/line.png" />
              </v-btn>
            </v-card-text>
          </v-card>
        </v-scroll-x-transition>
      </v-col>
      <v-col> </v-col>
      <v-col class="pa-0" cols="6">
        <v-img
          class="elevation-purple"
          transition="slide-x-reverse-transition"
          :src="require('@/assets/bg.svg')"
        />
      </v-col>
    </v-row>
  </v-container>
</template>

<style scoped>
.polygon {
  clip-path: polygon(23% 0, 100% 0, 100% 83%, 37% 98%, 0% 38%);
}
.bigFirst::first-letter {
  font-size: 3em;
}
.elevation-purple {
  filter: drop-shadow(15px 5px 35px #5353cb);
}
table {
  border-collapse: separate;
  border-spacing: 0 0.5em;
  width: 70%;
}
</style>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      show: {
        profile: false,
        hello: false,
      },
      profile: [
        {
          label: "Full name",
          data: "Wongvarit Pancharoen",
        },
        {
          label: "Nick name",
          data: "Oak (aka. Glairly)",
        },
        {
          label: "Student No.",
          data: "62010787",
        },
        {
          label: "Age",
          data: "20",
        },
        {
          label: "Gender",
          data: "Male",
        },
      ],
      social: [
        {
          icon: "mdi-facebook",
          color: "#3B5998",
          url: "https://www.facebook.com/oakfap/",
        },
        {
          icon: "mdi-instagram",
          color: "#E1306c",
          url: "https://www.instagram.com/oakfap/",
        },
      ],
    };
  },
  created() {
    setTimeout(()=> {
      this.$set(this.show,'hello',true)
      this.$set(this.show,'profile',true)
    },150)
  },
};
</script>
// https://line.me/ti/p/~oakfap
