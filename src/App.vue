<template>
  <v-app>
    <v-app-bar
      app
      color="blue-grey lighten-4"
      light
    >
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          :src="require('../src/assets/rise_logo.png')"
          transition="scale-transition"
          width="150"
        />
        <v-btn href="../" plain>
          <h1>信頼性ＨＰ</h1>
        </v-btn>
      </div>
      <v-spacer></v-spacer>
      <v-icon>mdi-account</v-icon>
      <v-menu offset-y>
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            plain
            v-bind="attrs"
            v-on="on"
          >
            root ▼
          </v-btn>
        </template>
        <v-list>
          <v-list-item
            v-for="(item, index) in items"
            :key="index"
          >
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>

    <v-main>
      <HelloWorld/>
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld'

export default {
  name: 'App',

  components: {
    HelloWorld
  },
  data: () => ({
    items: [
      { title: 'ログアウト' },
      { title: 'パスワード変更' },
      { title: 'ユーザ管理' }
    ]
  })
}
</script>
