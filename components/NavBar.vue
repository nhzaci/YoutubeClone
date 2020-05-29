<template>
    <v-app-bar
        dark
        app
    >
        <!-- Left of Bar -->
        <v-app-bar-nav-icon @click="drawer=!drawer"></v-app-bar-nav-icon>
        <v-icon class="mx-2">
            mdi-youtube
        </v-icon>
        <v-toolbar-title>YouTube</v-toolbar-title>
        <!-- End of Left of Bar -->

        <v-spacer></v-spacer>

        <!-- Center portion -->
        <v-row
            align="center"
            style="max-width: 500px;"
        >
            <v-text-field 
                single-line 
                outlined 
                dense 
                hide-details
                color="white"
                append-icon="mdi-magnify"
                placeholder="Search"
                @click:append="search"
                @keydown.enter="search"
                v-model="searchText"
            ></v-text-field>
        </v-row>
        <!-- End of Center portion -->

        <v-spacer></v-spacer>

        <!-- Right of Bar -->
        <v-btn icon>
            <v-icon large>mdi-video-plus-outline</v-icon>
        </v-btn>
        <v-btn icon>
            <v-icon>mdi-view-grid</v-icon>
        </v-btn>
        <v-btn icon>
            <v-icon>mdi-bell</v-icon>
        </v-btn>
        <v-btn icon>
            <v-icon>mdi-account</v-icon>
        </v-btn>
        <!-- End of Right of Bar -->

        <!-- Navigation Drawer from here --> 
        <v-navigation-drawer 
            v-model="drawer" 
            absolute 
            temporary 
            app 
            clipped
        >
            <v-list nav>
                <v-list-item 
                    v-for="route in routes" 
                    :key='route.title' 
                    nuxt
                    :to="route.path"
                >
                    <v-list-item-icon>
                        <v-icon>{{ route.icon }}</v-icon>
                    </v-list-item-icon>
                    <v-list-item-title class="title">
                        {{ route.title }}
                    </v-list-item-title>
                </v-list-item>
            </v-list>

            <v-divider></v-divider>

            <v-list nav>
                <v-list-item v-for="route in library" :key='route.title' link>
                    <v-list-item-icon>
                        <v-icon>{{ route.icon }}</v-icon>
                    </v-list-item-icon>
                    <v-list-item-title class="title">
                        {{ route.title }}
                    </v-list-item-title>
                </v-list-item>
            </v-list>
            <v-expansion-panels>
                <v-expansion-panel>
                    <v-expansion-panel-header>
                        Show More
                    </v-expansion-panel-header>
                </v-expansion-panel>
            </v-expansion-panels>

            <v-divider></v-divider>

            <v-list nav>
                <v-list-item-title>
                    Subscriptions
                </v-list-item-title>
                <v-list-item v-for="route in subscriptions" :key='route.title' link>
                    <v-list-item-icon>
                        <v-icon>{{ route.icon }}</v-icon>
                    </v-list-item-icon>
                    <v-list-item-title class="title">
                        {{ route.title }}
                    </v-list-item-title>
                </v-list-item>
            </v-list>

            <v-divider></v-divider>


        </v-navigation-drawer>
        <!-- End of Nav Drawer --> 

    </v-app-bar>
</template>

<script>
export default {
    data () {
        return {
            searchText: '',
            routes: [
                { title: 'Home', icon: 'mdi-home', path:"/"},
                { title: 'Trending', icon: 'mdi-trending-up', path:"/trending"},
                { title: 'Subscriptions', icon: 'mdi-youtube-subscription', path:"/subscriptions"},
            ],
            library: [
                { title: 'Library', icon: 'mdi-library' },
                { title: 'History', icon: 'mdi-home' },
                { title: 'Your Videos', icon: 'mdi-trending-up' },
                { title: 'Watch Later', icon: 'mdi-youtube-subscription' },
                { title: 'Liked Videos', icon: 'mdi-library' },
            ],
            subscriptions: [
                { title: 'Jeff', icon: 'mdi-library' },
                { title: 'Adams', icon: 'mdi-home' },
                { title: 'John', icon: 'mdi-trending-up' },
                { title: 'Abraham', icon: 'mdi-youtube-subscription' },
                { title: 'MKBHD', icon: 'mdi-library' },
            ],
            drawer: false
        }
    },
    methods: {
        search() {
            console.log(this.searchText);
        }
    }
}
</script>

<style scoped>
</style>