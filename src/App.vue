<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app>
      <v-list-item v-slot:default="{ active }" :active="active" to="/" expand>
        <v-list-item-avatar>
          <img
            src="https://scontent.fvca1-3.fna.fbcdn.net/v/t39.30808-6/296286978_601315298234897_8702199302445933680_n.jpg?_nc_cat=103&ccb=1-7&_nc_sid=09cbfe&_nc_ohc=vGBmgvF2f8wAX9ZHLS7&_nc_ht=scontent.fvca1-3.fna&oh=00_AfB68hMK3zc8hQW1LvxOQwpyuCAkit2dkc-CbdAOMP-DPg&oe=64552D61">
        </v-list-item-avatar>
        <v-list-item-content>
          <v-list-item-title>Quach Duc Thanh</v-list-item-title>
          <v-list-item-subtitle>thanhsilva@gmail.com</v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
      <v-divider></v-divider>
      <v-list dense>
        <v-list-item-group v-model="selectedItem" color="primary">
          <v-list-item v-for="(item, i) in items" :key="i" :to="item.link" link>
            <v-list-item-icon>
              <v-icon v-text="item.icon"></v-icon>
            </v-list-item-icon>

            <v-list-item-title v-text="item.title"></v-list-item-title>
          </v-list-item>
        </v-list-item-group>

      </v-list>
    </v-navigation-drawer>

    <v-app-bar app icon>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Application</v-toolbar-title>
    </v-app-bar>

    <v-main>
      <router-view>

      </router-view>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    drawer: null,
    items: [
      { title: 'HOME', icon: 'mdi-home', link: "/" },
      { title: 'ADD POST', icon: 'mdi-book', link: "/add-post" },
      { title: 'About', icon: 'mdi-help-box', link: "/about" },
    ],
  }),
}
</script>
