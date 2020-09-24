<template>
  <div class="events container">
    <h2 class="subtitle is-3">Check out our projects</h2>
    <div class="columns is-multiline">
      <div v-for="event in events" :event="event" :key="event.id" class="column is-one-quarter">
        <router-link :to="`/event/${event.id}`">
          <EventCard :event="event" />
        </router-link>
      </div>
    </div>
  </div>
</template>
<script>
import EventCard from "@/components/EventCard";
export default {
  name: "EventsList",
  components: {
    EventCard
  },
  data() {
    return {
      event: {},
      events: [
        {
          id: 1,
          name: "Charity Ball",
          category: "Fundraising",
          description:
            "Spend an elegant night of dinner and dancing with us as we raise money for our new rescue farm.",
          featuredImage: "https://placekitten.com/500/500",
          images: [
            "https://placekitten.com/500/500",
            "https://placekitten.com/500/500",
            "https://placekitten.com/500/500"
          ],
          location: "1234 Fancy Ave",
          date: "12-25-2019",
          time: "11:30"
        },
        {
          id: 2,
          name: "Rescue Center Goods Drive",
          category: "Adoptions",
          description:
            "Come to our donation drive to help us replenish our stock of pet food, toys, bedding, etc. We will have live bands, games, food trucks, and much more.",
          featuredImage: "https://placekitten.com/500/500",
          images: ["https://placekitten.com/500/500"],
          location: "1234 Dog Alley",
          date: "11-21-2019",
          time: "12:00"
        },
        {
          id: 3,
          name: "The Amazing App",
          category: "Websites",
          description:
            "The Amazing App is a mobile-app location based game in which the game for the mobile app is created using a website. A website is used to create the game then the game creators will send an invite code of the game to the team members. The game can be played in groups or a player can choose to play the game alone. The game is created with markers on the map where players have to physically visit in order to solve riddles and retrieve information then move on to the next level until all the markers placed by the creator have been visited. The team that solves all the riddles or that has retrieved information under the time frame specified by the creator will be the winners.",
          featuredImage: "http://the-amazing-app-website.herokuapp.com/static/media/map.71750df1.jpg",
          images: ["http://the-amazing-app-website.herokuapp.com/static/media/map.71750df1.jpg"],
          location: "1234 Dog Alley",
          date: "11-21-2019",
          time: "12:00"
        },
        {
          id: 4,
          name: "Rescue Center Goods Drive",
          category: "Adoptions",
          description:
            "Come to our donation drive to help us replenish our stock of pet food, toys, bedding, etc. We will have live bands, games, food trucks, and much more.",
          featuredImage: "https://placekitten.com/500/500",
          images: ["https://placekitten.com/500/500"],
          location: "1234 Dog Alley",
          date: "11-21-2019",
          time: "12:00"
        },
        {
          id: 5,
          name: "Rescue Center Goods Drive",
          category: "Adoptions",
          description:
            "Come to our donation drive to help us replenish our stock of pet food, toys, bedding, etc. We will have live bands, games, food trucks, and much more.",
          featuredImage: "https://placekitten.com/500/500",
          images: ["https://placekitten.com/500/500"],
          location: "1234 Dog Alley",
          date: "11-21-2019",
          time: "12:00"
        },
        {
          id: 6,
          name: "Rescue Center Goods Drive",
          category: "Adoptions",
          description:
            "Come to our donation drive to help us replenish our stock of pet food, toys, bedding, etc. We will have live bands, games, food trucks, and much more.",
          featuredImage: "https://placekitten.com/500/500",
          images: ["https://placekitten.com/500/500"],
          location: "1234 Dog Alley",
          date: "11-21-2019",
          time: "12:00"
        },
        {
          id: 7,
          name: "Rescue Center Goods Drive",
          category: "Adoptions",
          description:
            "Come to our donation drive to help us replenish our stock of pet food, toys, bedding, etc. We will have live bands, games, food trucks, and much more.",
          featuredImage: "https://placekitten.com/500/500",
          images: ["https://placekitten.com/500/500"],
          location: "1234 Dog Alley",
          date: "11-21-2019",
          time: "12:00"
        },
        {
          id: 8,
          name: "Rescue Center Goods Drive",
          category: "Adoptions",
          description:
            "Come to our donation drive to help us replenish our stock of pet food, toys, bedding, etc. We will have live bands, games, food trucks, and much more.",
          featuredImage: "https://placekitten.com/500/500",
          images: ["https://placekitten.com/500/500"],
          location: "1234 Dog Alley",
          date: "11-21-2019",
          time: "12:00"
        }
      ]
    };
  }
};
</script>
<style lang="scss" scoped>
.events {
  margin-top: 100px;
  text-align: center;
}
</style>