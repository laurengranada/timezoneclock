<template>
    <v-app class="app">
        <v-app-bar
            app>
            <v-toolbar-title>It's About Time</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn
                href="https://github.com/vuetifyjs/vuetify/releases/latest"
                target="_blank"
                text>
                <v-icon>mdi-account-circle</v-icon>
                <span class="ml-2">Lauren Granada</span>
            </v-btn>
        </v-app-bar>
        <v-content>
            <v-container
                class="fill-height"
                fluid>
                <router-view></router-view>
            </v-container>
        </v-content>
        <v-footer app>
            <span>TimeZone by Lauren &copy; 2020</span>
        </v-footer>
    </v-app>
</template>

<script>
export default {
    name: 'App',
    data () {
        return {
            //
        };
    }
};
</script>

<style lang="scss" scoped>
.app{
    height: 100%;
    width: 100%;
    .app_content{
        background-color: rgb(138, 138, 138);
        overflow-y: auto;
    }
}
</style>
