<template>
  <v-container class="ma-0 pa-0" fluid>
    
    <!-- Start of Navigation Drawer -->
    <v-navigation-drawer permanent absolute clipped :mini-variant="true">
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


    <v-row style="margin-left:75px;">
      <v-col>
        <v-row>
          <v-btn class="ma-1" rounded v-for="filter in filters" :key="filter">
            {{ filter }}
          </v-btn>
        </v-row>

        <hr style="border-color:gray">
        
        <v-row
          align="start"
          justify="start"
        >
          <VideoCard class="ma-2" v-for="video in videos" :key="video"/>
        </v-row>
      </v-col>
    </v-row>

  </v-container>
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
      videos: [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20],
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
