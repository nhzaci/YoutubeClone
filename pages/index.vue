<template>
  <v-content>
    <v-container class="ma-0 pa-0">
    <!-- Start of Navigation Drawer -->
    <v-navigation-drawer permanent absolute :mini-variant="true">
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

    <v-container class="ms-12">
      <v-col>
          <v-row>
            <v-btn rounded v-for="filter in filters" :key="filter">
              {{ filter }}
            </v-btn>
          </v-row>
          
          <v-row class="full-width" justify="start" align="start">
            <VideoCard v-for="video in videos" :key="video"/>
          </v-row>
        
      </v-col>
          
    </v-container>

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
      ],
      cards: [
        { title: 'Pre-fab homes', src: 'https://cdn.vuetifyjs.com/images/cards/house.jpg', flex: 12 },
        { title: 'Favorite road trips', src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg', flex: 6 },
        { title: 'Best airlines', src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg', flex: 6 },
      ],
      videos: [1,2,3,4,5,6,7,8,9,10],
      filters: [
        'All Genres',
        'Gaming',
        'Sports',
        'News'
      ]
    }
  }
}
</script>
