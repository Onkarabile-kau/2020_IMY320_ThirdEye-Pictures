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
          name: "The Gaming centre",
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
          images: ["https://lh3.googleusercontent.com/RH0A3uPXc2BVMHRI_LH3ybd6pTC_zk0ap-uKbFmSDe8ko6gYTPepNMKQ7DIQyZUms1eGbPOLpd4fzvgUXCyhDVkqKEEFdsvwqlN5SOfN49RVkgzx2X6N7XyE9MW4faAMi1VRssxQjIa_5YsRLIt-LXYyKIGtXlmXKoaG9ejkWa0acFRjj6I4VdsrEPBR-byGGdoXAA0wkrDocZlohZL4ahioUBnj7YKwrZ0JJXURBC9FS7OQVfDtVghw2sQHYuOfS8h7UMMrwCo-x2-ihzL2P8pnlfKJRx7wkqAJU3XjQXXnUJotMzd4aiWP5Xy4_LfEZ7NcZoa64OfsBYD4Np4oiHUW_YXQf4YRT2VPCUBckuk-AueETbiSSHVgRjJlmxM81oP4ot-auByjyX2M9BXX_MXYHMO3zL5va15qv0DThuhQ6-NwkKImKdbofoB26Cvl6DCtV1_EtLDiagA65QbLAuGtnzFzfkNhlMjdzMRmVRJXZfaagq4M2uz19wTXp7YCm4gXp6zlF94A3avvBd50o4_DqNA99FG69zuWxg0daNs8GNJVYW2ALymQzhbtUocrlVZg3L125a2Go3e1jUabfM2eSdBuVQfO6QZghzLmZOw5cbjAPZDalwfRD6E3h4eHt-68IN1aZ3Ix-I0VCiQlebwU8btHV6lxrZuPKTv_o_-4U65vbzlWgDgPH3bD=w292-h618-no?authuser=0",
          "https://lh3.googleusercontent.com/IHz72LGRrvdEKT5UWnYKWXOks4Ww1_2VEFzh-KeoxEFLY1UWXb05jMsyy8wk6hCVjJg05PhUgnUXKg9RlnMnlFXAb7C2ixtUh-nucuRIJojNruJsLoPMJCxTi96pi8OBn6rZipCSigP2CT8DW6Rla3UuptnOwIn94Hmr_-RseIwaliXA3g7Vo1GEzXWsQVaXfaxq-y1YqOhxgT4VNuSSdVVCYsVwgngnC5AsDAelCsbMwxm4VspMufROeQNQa5cdHU62ojiLJj2CTDoTFMHOksb15wPqWco4EjAgqtYw5cZGSn47lNkZmQ93W_WWeYKJUHRVP3ZdHU1zfybedvbUeS_QEAoxS0fqIgaUl74NOgoa99kIY6uHn5jfB8Tb5UHtUWrGleJ8guSAAoumY_Lk4en0tLWnME3Ty3j-6ratt2TNmnmV7JNSsHtXhqg7Z7NVF_ympUTAuAT6Q1FUa_wW1BLvRrsON4vGKlqMQAIUIVDN0zQtmquYQjKUJmDInC9562QSC8MAeL2BZRcD6QqlqCOgBN4iyzIl9Y8cczw-fmuj-LjJksKNQdH5zAMFgv5utUwf2HQLdjgitfwv9qqdvAJTVXvZBeVQUgu24WatxKHHUvIaTjpzl7ICDycSkpN1LCG6caDZyhjEKKJwS4FGn9VMZlImxH3_M7CmfjNzYhqKC9m1nODVuogKGRHI=w337-h657-no?authuser=0",
          "https://lh3.googleusercontent.com/NS7g1B2cNHfZNVg24xeR_5bfJvtHBT3myR5WMlF1ZFBFbsBWNZs8i9E0kSwOpZ6YuIzNEfaZbARDNCOt046otz1BWHXmMAcSpH4jB0oTzt4PGrjEq8EmfkOFcekTA6U0Ipds59T5iWlyKC0UJmDbKzLioPQcgDUVbG1v7yofxhHCQlWsGRmRvDZ0rh_nDe7Cv4plz0FEAZqz5X5nKLXXJ1r9Ef0319guYHqMbaVn5adHm_Lv8BAkuU6DSy1u2hcZsPtB_4aZeK27b6stulj52XJB_G9MmMX3OQrRkO2aqT1fxs_tOe4EUGRzk11BT5M1jInjWEBmxLnBtPddh-LfGsAWNAk700rurBR97aiM-h-JREK0JKUzHpCfB4upwxzVcWxa06yp3LBTFGHvX_2vFrQOsz3ciXAf144RAFB8Jhszx6taA9zAqaBZduJOco0j77p4gqWgIahOp063d09mfPntlf4x1szitaAZ5KstZd-GO1hvyMDmrEsL2QDHuoXC4IYKvXr_PilDMMh8DO-gM4ztPaRp9tzoWtenCHmsu3jTDKvLUhvsIevhZHeP-VdYbMDroTNeRcy0Fwh7KChwcNeljJyxJDrpuCjxpqkua8ZbTZmd7oy5KV8TvlOWTGaRWGB3Pq4vR5fjwNWdt8KyyPITXN4s7ACo4fHfDl0zlZz2nw0zxRlvulhcUIXX=w321-h634-no?authuser=0"],
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