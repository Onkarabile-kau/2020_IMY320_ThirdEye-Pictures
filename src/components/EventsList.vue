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
          name: "Gaming",
          category: "Gaming",
          description:
            "Come to our donation drive to help us replenish our stock of pet food, toys, bedding, etc. We will have live bands, games, food trucks, and much more.",
          featuredImage: "data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wCEAAkGBw8QEA8NDw8PDw8QDxAQDQ8PEBAODw8QFhEWFhUXFhUYHSggGRoxGxcVIjIhJSorLi8uFyAzODMsOCgtLisBCgoKDg0OFxAQFyslHyYuLS0tLSszLSsvKy0tKzUtNTctNystMC0tKy0rLysrLSsrLS0tLy0rKy0tKystLy0tLf/AABEIAKgBLAMBIgACEQEDEQH/xAAbAAADAQEBAQEAAAAAAAAAAAAAAQIEBQMGB//EAD0QAAICAQMCBAQEAwUHBQAAAAECABEDEiExBEEFEyJRMmFxgQYjkaEUQlJicrHB0RUzU5Ki4fAWNENjk//EABgBAAMBAQAAAAAAAAAAAAAAAAABAgME/8QALhEAAgIBAwIDBwQDAAAAAAAAAAECESEDEjFBURNh8CJxgZGxweEUMtHxQmKh/9oADAMBAAIRAxEAPwD8dEoSBKE60crKlCSIxGiSxKEgShLRDLEoSBKEpEssShIEpea5J4HcykQz0EYmw+D9UFXI2DIqOLUsAtiyLo71sZ6YfBeoe6RdlLb5cQsDsPVz8pokzJzj3RjIIqwRYsWKscWP0MYmgeHZ9rR9NXqpmVRf9m+/+M8HWjVg/MGxGLkvGha6BNAs1dgO8Y9+08wf1jBlJktHoDK+X/eeYMoGUmS0egMYM8wZQMqyWj0uO55gx3Ksmi7juRcLhYqLuK5NxXCwoomK5NxExWOiiZJMVxExNlJATJJgTJJktlJATJgZJMlloDIJjJkmQykhGK4ExSWWjliUJIjE5DtZYjEkSpSJZQlCQJQlIhliUJAlAykSzpeF9EMls5YKCFVUGp8rncIg96/y9511zDESgyr04UVSoVNcNqN62bmodVhfFj6fF0x15WQjWloE2DuQTW/rI1HgDb3mUdH02NVVhkz59TjJTaMAICmthqNWbbj9JulRyuW7JZ6vASRk6jO6sxYkJr3F1QyMK5PuRfM8h1XS1RXPdg8oV1Djb6E83yfczb1Pl4W8tl6QkHfy08wX7B2G/wC88T4hj/m6fpq7nQyk/Sk2jJWeEyP43EKKO6NtZIsMPau3f6/49PIvm4whOvReVGXy31s2MHQ5H81Ct/hI+cyr0HS5cRzhhjpgvlqxVmNEkqrj1AfIj9Z6+CY36fOceptGfGVtfSTRDUbHIFn9PeXGzObVNrldzjZMdHdCgI1LW50GyDRO+1d+0eZLvICpF76Rpq/7NbcTR4p02RC3mjSUbQqkaSb9Wr58g/O+ffnlr3O/1k8GqyrLBlap5gxgx2Kj0BjuQDGDHYqLuO5Fx3Ksmi7hci4XCwou4rk3C4WFFXETJuK4rHRVySYiYrisdDJkwkkxWVQyZJMCZBMlspIZkmBMkyWykgMkmBMVyS0c0ShIlCciOxlCUJAlCUSyhKEmMSiWWJUgGdLwzwnJnDOpVMasqM7HeyCaVeW2Hb3HvKVvCM5NRVs+kLB0VVpCmHHk1Wbzu2NQMQ/p41H32E4WLKWsUVCujMDy1BiNXyJ0j7zf40AuTDiBdawImPUdtQxFbAHw2SD37bzLi3xvlIO4XWBXKkOWUjsaB9rvjabyeTm01Ub7mLLlJAyc6iVcHcEg2L+xA+09Onw2RWzHcISeObv2reufrKwdMRjyEKz1TKa9GMqCT5nsdJJrjbvA4/LsOSGsHLY3FbhCT34Jq+3tJNR5crmyA2zIEBWyNm/efQfhrMjlUdQzI35Wk15bkVQ7MDdVxuPYTg+eNBxqn8++Wz52kDYWNq34r23mvwbV5yEGx8IUi3vkD9QL3+00g6aMNaO6DRP4gYt1GUkV621GhuQzBeBtsAK+VzmmxsdiNiDyJ9D434Wvm5+oVmPTgg5aKDMrM4G6E7+o9u1fWfOGr24va+ajlhi0WnBUepHccXV8RAyD+sYMmy6LuO5EdyrFRdx3IuFx2Ki7juRcLhYqKuFybhcLCh3C5NwuKx0OImK4iYrHQyZJMVxXFY6AmImBMkmJsqguImBMkySkgMm4zJuSykjnxiTHOU7ChKEgSpSJZYMcgShGSywZ9Qzr/CdGcTEKEdcytW+XzG1kqOV0n72Pbb5UTu+EMG6fNeQI3TnzMdH1kZQEYgWBQ0i7/rmum+UYaq4fZ/j7mnr/AC8h6dl1a0xLShtRyMMjE88HttYNDeUGPRsE0hfSVfzuNDbn0EG23HA2ofby8S6VfL6dvKCKqZC+nVpYq5Jon31Abf0zL1uV8uV8uQHKW0szHZidIsluy3Y322ofK26M4xtV0z9Tf03iC4H80Y1zABwfNUaaNgqVHI9idj7c1g6l1dm9Sh75q8L/ADUkal+hsfMT18rHoRxmR8j2uTCQR6V+Ea60kH5f0AiSvRsQHTGSi/ExHm6fYEj0nfaxz8twHb4GlFOyzjdcaawUQltWQKANQVaAYfFtWwPczR4PjZ82OgxQnQrcluL37UDZH6zOvUO6HC+WkDasaavM0sTTbD072Lsj9p0fwsB/EY1GNmYHUf8A42LUSo0r32vngmVHMkZara05P3m/qOrT+PbGiaQ7ldBOoEVtRPPHH+M+b8Xx6Oozp/TlddlC7hiOATX6zu9P0581s+SxiUtkzMvrK0TYHBuq7z5fM9sxBJBZiCRpJs3x2+kqb+pGjFLjshgxyLjXfb/MCRZvRVyrnncdx2Ki7juRcLjFRdwuRcdwsVFXC5FwuAUXcVybhcLHQ7iuK4risdDuImKImKx0O5JMLkkybKodybgTETFZSQEyYExXJKMAjkiVOY6hygZMYlElCUJAlCMkoT36XqXxMHQ6WFj3BB5BHcfKe/ReD9Rl0sMZRH3XJkvHjYe6k/EP7tzr9B4T06jJkZ1zLjW7YrjXKLo+Ul6nPzsbXNYxfJjPUgsPJ0PCuqfqVbF/DjTgOPOQHOdPLLBnXSTQBH2BO9Tl+IdQcmg0iltWnGBjI2Y8KQaaiPSaP1lYvHcyH8jEMWNV+DGo0P29VbG73r5zX1XRY8+Feqx5LyDJkLYW1hhYHxn+q6/vc3ua2vcsM50tkrapPjr8zl9OrOXQZhjABot+TbJvQ07En1UL5M9B1OTQ2NnYLkYJuXOoqLGrs25Xb6zMFdzT7lPhIBV8fsKYCx9f1mvqeidPLW1a01gYcisyamOzAG6oKK527SFZs6vJn6Pp1d1BZUDHScg1aACKJIrbazt7cT6Pw7pC3m5l0uVVlC6lx+ZbaLFkdvl/LOZ03huUnU2PZ6CqBV6u1dgWvkD4TNnjLLjxoiZaIYnP5d6gwUAWeK9R4sTWCpW0c2tLc1GLMPXv1BTyMqnCga8WNselAdt/M5J25ax9LnJZGU+pa5G87fSfiLKisurzNIHlpk0HGBfq1BrJ5vntPZupw58ZdunwqNQU+XlXE4cqeFv1D6D2vtCoy4YKU4cxx5HE/gnFax5QPfJa96O3PY9u0nJiCi9SMb/lazVe1TpHwfHkYDDnQMT8GYjG2/8AavT+pEw4ulIc43BU6WOlvSzACxpva9tveS00aRmmZrjlZtNsRQpgoUXZFHe+O37yBZ2552/xiKoosfrC5FwuFhRdwuTcLjsKKuFybhcVhRVxSbhcLCiorkwuFjodxXETETFY6GTETFcVybHQRXETFEUEUDFcQ6MMoGRHOY6i45IMcokoGfQ9H4cmJNecJkdgj48NbLYOk5G7Dn02BYHPbJ+Hunxnzc+VSwxY2OFf5WzjdQw5ZQoY0O+ntc9fEer9ZBt8hyOw1elFBNCgvbSObv7XNY4Vswm3KW1fE2db1i03mOM3UBSmFhYwYsZZVZQp5BBoDYDUdjdTj5hkNM5IctqJc6SAuy0ORXq2Hynn/EMdek16QAF9JPrX23PP7ynAYnvo9I/+wKOPr3+h+ljlY4w28GhExnFkZn/NOhcdLWN7ayWJqj6eaon7mPw7xHLhLkG/SA6PupAcAgjtz2+cx2SvuWfgeyr2/wCabejwIyv5+TyvyrxmtbOdS6VIHA/tHj5jhp5wKSVOzqt1fRZQMuTI2LLqNIyNkXFsN7UUy2dtrFfS6xjpFNvltlQkKRlGvSCf6QxJ/tGpwGBGyaVI2Pq0vf1av2qTiRgwtSATpsgj4tv85e/yM/B/2Z9EfxDnpkxhcOFhpYrTM/YLrHG9bDf5mcl7Td3/ADHZtYBB0ChRIHeydvaxIxZ3wFTjJGZSG2AOlvmO5HseN5TM7DVpyD30ahpP04I/T/Ucm+Qjpxh+1FdN0ru4REbWxKBFUkMTsNP3PH6e088iaTpYgBbUgmyTfq2HBv3rgT26fpcj3kSy2JSxJOhq2Cn1EbhiOL7e0jLiezaBlO49SggHegfv8xAfXkMWXQV0lmFirNLz/T/3nQfr1ytkVkx4yWIxFQyrjbXq1IbtTwPY37zDg6DIxVEUsWYaF2L6u1Ac9uP0j67pmXI2wQB22e1AOonuPt9pSbREkm/M9M3RqNb6moF9S6QCu3p77gkgX/rMQQ0TsKqwSAd+KHJ+07eHpRnwMWyYzlV7xY0+J9XxaRVAD0n7EDicNkOpwoYhbO43Cg8tXHaOSoUJXa6oVwuTcLk2XRdwuRcLhYUXcLkXC4WFFXC5NxXCwoq4riuK4rHQ7hcm4XFY6HcVxRXFY6HcRMVxXEOgJiuK4RDMccmOc50jlrZ2AJJNADck9hIE7X4W6ZGynNkNJ04XJX9TWdIB7Ha/tLirdETlti2bOpypgx9OqhfMwOrsFLfmAE6sj77gta7Vaos5vVZEt2ZKZ2b1KWba6OxbbcEc+/yjbp2bLrHmPqYn0pWleKaxt6dqqjwJsOEZcjjEiYuXVMj6hiXvqfmuOAN63M0bsySUeTy8K8OfJ5mRFtEx6mfXoAp1r46s3WwnmOkBIAu12pWsL9SBz+m82p4fiONsmbrMbNrVfLCZVPBNCwDXHYb1zHjXpSG1jq86/AihFXy32JIGmyABxt8Qj2k78v8Ah/cy50GlQmosdTNqxFMW5oUN7O3823+WZ+myhCzJk9b0GKsQ2kWfVwfiWd3P+HVK4jgTKx0NrGfSpX1EjSK32P8AMB22kr+HOqYaGw9Q67lR5mFQre62aHtxx9pfhy7Gf6jTS/cvicTHhd6TQ+o0EOk7+yn/ACP+XFq2Tpsn8yZ8bbjg4nU9/wC1f6fXjur+EOtO2PpyAexdRf1KmyPvNHUfg3xDUxydMWGptLqdR57lm3H6w8OXYX6jSf8AkqPn+r6pmZ2YljqbXuVN38W3ufe9/qJnRhdht+CH3BHtY5/afQ5vA+vwvqTDi1FeQMGU+paYHV33PaeH+yOpOknEy0CcoOQY1ABJJUhqqq53+sfhy7MFr6fSS+ZzW6LIqeYFIRmVVyNQW6JK6+L+ExscVKXJdt1JxjSNje5bnn27czYPDsrMEVkxYy4AXL1HTtjBJq2p7u+9E7fLZ/8Ap7OQ+gI1DXS5UYkKatQDbbE7Czt3htfYfiR6yRz2zOvwaUXscVi/q3xX8jGNQZjuQWYhBZ178ke3z/8AAdGunIlLqOpb8ykxEX/MDyux5oSeq6hspbITydTooCqpJ7KNtPYe2w9rmy6yb/CMq+dj80hQWAbR6qUc+nji9rEy+L9N5WbJj7BrU+6ncftUzYXKhmG3Cj68n9h+87P4jVnx9N1JFgoMLEEFdSgMosbXpYfpNFmD8jGXs6q88HDuO4tV8k8bbXwKAiuZ2bUVcLkwhYqKuFyYQsKHcLiuK4WOiriuK4rhYUVFcVxXFY6HcVxXFFY6HcUVwuIdBcVxXC4h0ZI5McxOgqdxFXH06ISScinPlC7EhgVxr7kUQfa252nH6XFrdU7MwBPsvc/pc7WfM/V5Xc5Cj58uPHiDuwUoxpCT/INKgWdu+0uPUynyu3r18DJlbIq+So8kP/vEBKsw7Kw+J/0O9CtjNovD0uIYyhfPlyDKQaDomkBNzvux4E5/VhVyZF1F3Lv5jL33NgO3A53o2PltOp1+RUXD01BTiUqx3GTIXF0pO1jiyABZG+4lx6kSzt+f/P6HjGDp/wCHfLjx59eRScZJGE4tfrJCn49lFcDfaefjni3UDJ5WoY0xgogxKMIO3q3Xc017EmqA3h1HUN064VrGAhyaNWLHkyarQ2pYHTW2988Aiptx+J9d1OMKcxXHzjXLixnUSfUwOimvfc6RLvoZOLtSaT97+mGfODqsn/Eyf87f6z0HX5v+I4+jEf4T6BvDPO/3+B8bCsYz4sRwoWAAQEUEJNjhb2Jszkdf4LlxhHx6s+LIDoy40arAtlI3ogb/AE+8TjJZRanCWGef+1up2Hn5thS/mPsPYbxjxfqf+Pm//R/9Zi8tudLV9DEu5CjkmgO5MnfLuV4cOyNp8T6g85sv/O3+sS+IZgb8x242di6ne9wdjPDDgdyAiO5Y0oRWcsfkAN50R4WuP/3GTQ294k0lx8mJNA/S/nUpOTJagsUbh1uLMM2Ss3TY0AbTjbHkAZvalQ7ke553948V4s/oy3Tq+NlDay76SAeNKlTVE7/Pt4Yf4YDyijth1JlyM2bQxpONsdUNTbAn4vpPXqesxtkfLhTLhzMyt04XIrhsYoeoFQSKFab97ua3fLMdvRLHw/s8vF2C5864kKBTksajkDsz0diSK3O3yNzGjAuWGNVF3p1VS9w3yr5Cdfx7CXJ6gU2LNpasQ0jGwXddhpG5PPz5nEcr8IIoH4D6B9ST8X7fKRPDZelmKNnW4MYGPyfzAyHIwNacZLkEVZJX0jdj9Rvvu6BGzdNkxkeZovKmPUQtoLYg7AAKTx8hOUuoqhJ0KhbVtQA547/95t8HdcubR8Cuj4ynZEKMNvcb3795UXn3k6kfZ92TH1WIlTlUAKTqZQAoUGtJA9jZFDij2qY/nf23v/z/AEnr1WVidJolAMd6QPg9Pt8pnuQ2aJYLuEm4XFY6KuFybhcLCirik3CFhRVxXFCIdDuKK4rhYUO4ExXFcVjodxXFFcVjodxXFcUVlUZ4CKOZGx0/CdKp1GVsfmEY1x4wGIIyZHAvg36Q4r5z1wFQmcgO2clKOtWCWHG/pFtZHGwF/a+jZseDGigX1DksCAT5ZOkfb0Ob+f1vo9B1PT4sbKEVyWOjJpXGc53KKy7hAAD8zq77VrFcZOecmraV5MngnReZkxArrCOnmsbGMqCKVm4HYAXZ24oCV1mbqQyZsp6hHIR0OMuuVSQGVlI2Aoir9tpny+J5srMWyBFWguNSyKnqBqiBfpVv34nrm6bUAz47TIA2JcLDIEbdiCVs6AGquRfbeUmqwKnuuRWB+oONjoD48eRH15FYpjVgQS+vbkL8QNni9psHW5Mz4sQxr1Dg6icmDXrBAIBoAE6QK2X4tyeZn6TwbK48vS/IY4tAVePTdHTdGwCbOrvW9dZnOInFm645At6cWAvmUGgd3Dr9CA3v7VKVpZIltbxV+vXQ6nQjMv5eRc/TqSHTyfMCKAL9WElkJvbYA8VdzJ4v4n1eJz0xfAyowcBcY1MSo9ZFHSxFEgbbj2Ey4/xDiQOq48+YZF0umbKqYxtyqqDRvfnmfOr7Ry1FVRZMNFuTcl6+x3T43lB3YL/ewYx/1AA/tH/t7qANjYrsbWvmBOIrkcEj6EiWMx52v3oX+vMjxJdzV6UOyPqOm8RzZ8KjFnTDm/M89wdGXRZOxBsJRF9yfpPHF0eOmD5mysthgiKV9O25dlYn+7zsd974/Q+JvhyLlQKHUMFarO6lTeqwdiebnYw+JYcuNA3kDMGJZc+vEjb7FXSlU18hzNIyUueTGUHB+yseXrg82/g32Y5lAu2R0ptK7CtJ2FHiquScWMFnXKVCN+UCjnIdtltQR/Sew/WdHB0/TuQ46Zc7opvHi6ptL7H0hgSTzzXvMw8N6jI3lp07ggAIBrxiuyki7HP37UbjcWJTj3a99HR6f+Dy9IMWTOuDIOpfySAwdRoFM4GwuzY7E+1CcXr/AA3LhP5gYg7o+HU2N1PBsCgPpv8AKHjC4sOjAoTUttkyKVcDLdFSnahQvv7Gps6nqsuHF0+FsjVmxDIFxNpK5BaKxYdzwUI7b1tVNp4a4IhGUXcXh9H9vyeHSdZ1OPCyhWbFkyU6AehqS0Oog1R399o+gFvqTMcYpiVXIco1aWChlBNb1RurPAupkORnYg5Cbb81wLOsndig73t7EXW536HgGFq9Rxq6uVC2MbYxaO7E1p00g22/6t5i7aRpNKMWzl+O4dHUZQCSGbWGK6L1gOdrPBYj7TCWJ5N8Df2Gwm38QdQMnU5mV1dA5XEULFPLGw06t67/AHM58zlyzSF7VfYq4XJhcVlUVcLk3C4WFFXFcUVwsdFXFcUIgocLk3C4WOh3FcVxRWOh3CKKADihCIZmjkxzI2PsvEelwoh05Cr4guNbTWpxKgKuaNhrddqO2/czg4+lyAWrLkBYlypbIpAArUVHpO53NVPoMYTPjbPjIysWwvlRCcQTL5Wl0KkWRfBXbb5EzJ/AsCjHGqqvqKIXVlazQokUxHFqSN74udE43lHHpzpU3kyNgQoNWRB5p9IVlbIuk1RI2Iu+O3txNngXR9RjdsmHTpxqzsd862FOkuGGgAEg+oCqntnGVsevqXx9GiX5dY/L6nMtixuAzHijxVi+Jyet8eyFRiwNkw4lFEhz5uXteRgf+nj68wxF2wuU00vwdHxLxhsCnBhyPkZm1ZM+TMucldOyL3A+Hfa99q5+aJ/84kRzOU3Jm0NNQWCoSY4iyrjuTCAi4SbjuMVHpjfSQwAsXVgMNwRwfrPo8bHrsS064+owDdNWkdQg0259ms897+Rr5mNWIIIJBBsEbEHsQexlxlRnOG7PU6rdPkxsVcDSrAPlb/d4we2N/wCqvY9uNrnvkRVx4mAyEYdYXUAgGRm1epjXuCBQ5HNys/iGLrK80LhzBQCxfThykDdyxvRkO5P8p+W0Ov6TFjKF+oUYwpKJi9eVgTQoqaoqq+q+bA4Euua4M93Clhj8M6PzctIKQEM5D+XjVKDUzgA8HsT9Zfj3jaOv8Lgx40xihmyouls7ChZA2rYfXSPvz/E/F3zDywWGIABVJtmA41nuZzYOaSqILTcpKU+nCKPy39jxC5MJmbUVcLkx3AKHcLiuKAUVcLkwgFDuFxQgA4ooRDHFC4rgA4riuKIdDJhFFEM8YQhMzQ9cXUOoIR3UGiwVioJF1dfU/rNq+O9UNP572taSaZtuPURZ4EISk2uGS4xfKMWbMzsXdizNuzMSSfvJhCIYRwhGAR3CEYhwhCAgjhCMAjuEICHcBCEYhwhCABCEICCEIQAIQhAAhCEACFwhAYriuEIAFxQhEMIoQgMIoQiA/9k=",
          images: ["data:image/jpeg;base64,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"],
        
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
          name: "The Swift App",
          category: "Website",
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