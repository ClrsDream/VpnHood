<template>
  <v-app>
    <AddServerSheet />
    <ClientProfileSheet />
    <ErrorSheet />
    <ServersSheet />
    <ProtocolSheet />
    <AppFilterSheet v-if="this.$route.query.appfilter != null" />
    <IpFilterSheet v-if="this.$route.query.ipfilter != null" />
    <SettingsSheet />
    <v-navigation-drawer
      app
      :width="250"
      temporary
      :disable-resize-watcher="false"
      :right="$vuetify.rtl"
      v-model="store.navigationDrawer"
    >
      <Navigation />
    </v-navigation-drawer>

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<style>
html {
  overflow-y: auto !important;
}
</style>

<script>
import Navigation from "./components/Navigation";
import ErrorSheet from "./pages/ErrorSheet";
import AddServerSheet from "./pages/AddServerSheet";
import ClientProfileSheet from "./pages/ClientProfileSheet";
import ProtocolSheet from "./pages/ProtocolSheet";
import ServersSheet from "./pages/ServersSheet";
import AppFilterSheet from "./pages/AppFilterSheet";
import IpFilterSheet from "./pages/IpFilterSheet";
import SettingsSheet from "./pages/SettingsSheet";

export default {
  name: 'App',

  components: {
    Navigation,
    ErrorSheet,
    AddServerSheet,
    ClientProfileSheet,
    ServersSheet,
    AppFilterSheet,
    ProtocolSheet,
    IpFilterSheet,
    SettingsSheet
  },

  data: () => ({
  })
};
</script>
