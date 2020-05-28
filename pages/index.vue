<template>
  <v-content>

    <!-- Start of Navigation Drawer -->
    <v-navigation-drawer permanent>
      <v-list nav>
          <v-list-item 
            v-for="route in routes"
            :key="route.title"
            link
          >
            <v-list-item-icon>
              <v-icon>{{ route.icon }}</v-icon>
            </v-list-item-icon>
            <v-list-item-title class="title">
              {{ route.title }}
            </v-list-item-title>
          </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <!-- End of Navigation Drawer -->

    <v-container class="fill-height">
      <v-row>
        <VideoCard />
      </v-row>
    </v-container>
  </v-content>
</template>

<script>
import VideoCard from '@/components/VideoCard';

export default {
  components: {
    VideoCard
  },
  data() {
    return {
      routes: [
        { title: 'Home', icon: 'mdi-home' },
        { title: 'Trending', icon: 'mdi-trending-up' },
        { title: 'Subscriptions', icon: 'mdi-youtube-subscription' },
        { title: 'Library', icon: 'mdi-library' },
      ]
    }
  }
}
</script>
