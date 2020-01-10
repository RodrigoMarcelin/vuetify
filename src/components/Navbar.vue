<template>
    <nav>
        <v-toolbar flat app>
            
            <v-toobar-title class="text-uppercase grey--text">
                <v-btn icon @click="drawer = !drawer">
                    <v-icon>mdi-menu</v-icon>
                </v-btn>
                <span class="font-weight-light">Todo</span>
                <span>Ninja</span>
            </v-toobar-title>
            <v-spacer></v-spacer>
            <v-btn depressed color="grey--text">
                <span>Sing Out</span>
                <v-icon right>mdi-exit-to-app</v-icon>
            </v-btn>            
        </v-toolbar>
        <v-navigation-drawer app v-model="drawer" class="primary">
            <v-list class="primary">
                <v-list-item v-for="link in links" :key="link.text" :to="link.route" >
                    <v-row class="pa-5">
                        <v-list-tile-action>
                            <v-icon class="white--text">{{ link.icon }}</v-icon>
                        </v-list-tile-action>
                        <v-list-tile-content >
                                <v-list-tile-title class="white--text">{{ link.text }}</v-list-tile-title>
                        </v-list-tile-content>
                    </v-row>
                </v-list-item>
            </v-list>
        </v-navigation-drawer>
    </nav>
</template>


<script>
export default {
    data(){
        return {
            drawer: false,
            links: [
                {icon: 'mdi-view-dashboard', text: 'Dashboard', route: '/'},
                {icon: 'mdi-folder', text: 'My Projects', route: '/projects'},
                {icon: 'mdi-account', text: 'Team', route: '/team'}
            ]
        }
    }
}
</script>