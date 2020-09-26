<template>
  <div class="event-single">
    <section class="hero is-primary">
      <div class="hero-body">
        <div class="container">
          <h1 class="title">{{ event.name }}</h1>
        </div>
      </div>
    </section>
    <section class="event-content">
      <div class="container">
        <div class="event-images columns is-multiline has-text-centered">
          <div v-for="image in event.images" :key="image.id" class="column is-one-third">
            <img :src="`${image}`" :alt="`${event.name}`" />
          </div>
        </div>
        <p class="is-size-4 description">{{ event.description }}</p>
         <p class="is-size-4 description">{{ event.link }}</p>
        <p class="is-size-5">
          <strong>Category:</strong>
          {{ event.category }}
        </p>
      </div>
    </section>
  </div>
</template>
<script>
export default {
  name: "EventSingle",
  data() {
    return {
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
          name: "VFX – Whargharble",
          category: "Gaming",
          description:
            "Check out these IMY300 gaming projects at the following link below",
          link: "http://mm.up.ac.za/blog/?author=4",
          featuredImage: "https://i0.wp.com/mm.up.ac.za/blog/wp-content/uploads/2019/11/2019-10-23.png?fit=1146%2C498",
          images: ["https://i0.wp.com/mm.up.ac.za/blog/wp-content/uploads/2019/11/2019-10-23.png?fit=1146%2C498",
          "https://i0.wp.com/mm.up.ac.za/blog/wp-content/uploads/2019/11/2019-10-23-3.png?resize=768%2C432",
          "https://i0.wp.com/mm.up.ac.za/blog/wp-content/uploads/2019/11/2019-10-23-10.png?resize=768%2C432"]
        },
        {
          id: 3,
          name: "The Amazing App",
          category: "Websites",
          description:
            "The Amazing App is a mobile-app location based game in which the game for the mobile app is created using a website. A website is used to create the game then the game creators will send an invite code of the game to the team members. The game can be played in groups or a player can choose to play the game alone. The game is created with markers on the map where players have to physically visit in order to solve riddles and retrieve information then move on to the next level until all the markers placed by the creator have been visited. The team that solves all the riddles or that has retrieved information under the time frame specified by the creator will be the winners.",
          featuredImage: "http://the-amazing-app-website.herokuapp.com/static/media/map.71750df1.jpg",
          images: ["http://the-amazing-app-website.herokuapp.com/static/media/map.71750df1.jpg",
          "http://the-amazing-app-website.herokuapp.com/static/media/back3.3ac2f525.jpg",
          "http://the-amazing-app-website.herokuapp.com/static/media/logo.9d394f92.png"],
          location: "",
          date: "",
          time: "",
          background: "http://the-amazing-app-website.herokuapp.com/static/media/map.71750df1.jpg"
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
          name: "",
          category: "",
          description:
            "",
          featuredImage: "https://placekitten.com/500/500",
          images: ["https://placekitten.com/500/500"],
          link: "",
          date: "11-21-2019",
          time: "12:00"
        },
        {
          id: 6,
          name: "The Swift app",
          category: "App",
          description:
            "The swift app is a convenient, flexible, and scalable interface suitable for both customers and restaurants giving users the opportunity to order, track and pay for their food immediately while at a restaurants, providing contactless dining. The application will also use Augmented Reality to show real live photogrammetry models of the food, making the menu come to life. Accessable at :",
          featuredImage: "https://placekitten.com/500/500",
          images: ["https://i.postimg.cc/pTnbRT46/sw-ift-app-image.png",
          "https://i.postimg.cc/cJCGkTmZ/sw-ift-app-image-2.png",
          "https://i.postimg.cc/mkfxD4G2/sw-ift-app-image3.png"],
          link : "https://app.dev.swiftapp.ml"
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
        },
      ],
      event: {}
    };
  },
  created() {
    const ID = Number(this.$route.params.id);
    let event = this.events.find(event => event.id === ID);
    this.event = event;
  }
};
</script>