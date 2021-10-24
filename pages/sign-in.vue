<template>
  <v-app>
    <v-layout justify-center align-center column :style="bg" class="bg">
      <div style="width:100%">
        <div class="text-center">
          <v-avatar size="100">
            <img src="https://nuxtjs.org/_nuxt/img/logo.d0868f5.svg" alt="" />
          </v-avatar>
        </div>
        <v-card max-width="400px" class="mx-auto transparent glass-login">
          <v-card-text class="mt-4">
            <h1 class="text-center">Sign In Account</h1>
            <v-text-field name="name" label="Email" id="id"></v-text-field>
            <v-text-field name="name" label="Password" id="id"></v-text-field>
            <v-btn class="mt-4" color="success" outlined rounded block
              >Sign In</v-btn
            >
          </v-card-text>
          <v-card-actions>
            <v-btn text darl>English</v-btn>
            <v-btn text darl>Spanish</v-btn>
          </v-card-actions>
        </v-card>
      </div>
    </v-layout>
  </v-app>
</template>

<script>
const bgs = [
  'https://images.unsplash.com/photo-1451187580459-43490279c0fa?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1172&q=80',
  'https://images.unsplash.com/photo-1523961131990-5ea7c61b2107?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1074&q=80',
  'https://images.unsplash.com/photo-1496096265110-f83ad7f96608?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1170&q=80',
  'https://images.unsplash.com/photo-1550745165-9bc0b252726f?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1170&q=80'
]
const ranBg = () => ({
  backgroundImage: `url(${bgs[Math.floor(Math.random() * bgs.length)]})`
})
export default {
  layout: 'blank',
  data() {
    return {
      bg: ranBg()
    }
  },
  mounted() {
    setInterval(() => (this.bg = ranBg()), 5000)
  }
}
</script>

<style>
.bg {
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
  content: '';
  z-index: 0;
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  transition: all 1.5s;
}

.bg::after {
  content: '';
  opacity: 0.5;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  position: absolute;
  z-index: -1;
  background-color: hsla(207, 90%, 54%, 0.699);
}

.glass-login {
  box-shadow: 0 0 1rem 0 rgba(0, 0, 0, 0.2);
  border-radius: 5px;
  position: relative;
  z-index: 1;
  background: inherit;
  overflow: hidden;
}

.glass-login:before {
  content: '';
  position: absolute;
  background: inherit;
  z-index: -1;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  box-shadow: inset 0 0 2000px rgba(255, 255, 255, 0.5);
  filter: blur(10px);
  margin: -20px;
}
</style>
