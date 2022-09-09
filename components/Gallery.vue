<template>
  <div class="block galleryBlock">
    <v-container>
      <v-row>

        <v-col v-for="item in items" :key="item.id" class=" d-flex child-flex" cols="6" sm="4">

            <v-card @click="openDialog(item)" width="300" height="300"  tile class="d-flex">
              <v-img  width="300" height="300"  :src="item.src" >
                <template v-slot:placeholder>
                  <v-row class="fill-height ma-0" align="center" justify="center">
                    <v-progress-circular indeterminate color="grey lighten-5"></v-progress-circular>
                  </v-row>
                </template>
              </v-img>
            </v-card>

        </v-col>
      </v-row>
    </v-container>
    <v-dialog scrollable
              width="705"
              height="100%"
        v-model="dialog" >
      <v-card width="705">
        <v-card-title>{{ currentItem.title }}</v-card-title>
            <v-carousel hide-delimiter-background show-arrows
                        height="470" width="705" v-model="page">
              <template v-slot:prev="{ props }">
                <v-btn icon
                    variant="elevated"
                    color="white"
                    @click="props.onClick"
                >&lt;</v-btn>
              </template>
              <template v-slot:next="{ props }">
                <v-btn icon
                    variant="elevated"
                       color="white"
                    @click="props.onClick"
                >></v-btn>
              </template>
              <v-carousel-item
                  v-for="(item,i) in currentItem.pictures"
                  :key="i"
                  :src="item"
                  reverse-transition="fade-transition"
                  transition="fade-transition"
              ></v-carousel-item>
            </v-carousel>


        <v-card-text v-html="currentItem.description" class=" ml-n1">

        </v-card-text>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
              color="green darken-1"
              text
              @click="openLink(currentItem.link)"
          >
            Go
          </v-btn>
          <v-btn
              color="green darken-1"
              text
              @click="dialog = false"
          >
            Close
          </v-btn>

        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
export default {
  name: "Gallery",
  data() {
    return {
      items: [
        {
          id: 1,
          title: 'StemLink',
          src: 'https://i.imgur.com/R8JnSqt_d.webp?maxwidth=760&fidelity=grand',
          pictures: [
            'https://i.imgur.com/ya1h6AH.png',

            'https://i.imgur.com/I0xDNxi.png',
            'https://i.imgur.com/i0mwCrn.png',
          ],
          description: `StemLink is the interactive notebook for all STEM subjects with built-in tools and sharable docs for seamless collaboration. My responsibilities were: <p>● developing a new dashboard interface for faster access to shared, stared, and recent files<br>● upgrading existing editor library, along with creating new propriety extensions allowing the ability to add math, video, and graphing calculators to the editor<br>● developing new features for new editor such as the math keyboard, slash commands, and tables.<br>`,
          link: 'https://stemlink.net'
        },
        {
          id: 2,
          title: 'A-Zoom Manager',
          src: 'https://i.imgur.com/ILjG9wf.png',
          pictures: [
              'https://i.imgur.com/Cw6TVnE_d.webp?maxwidth=760&fidelity=grand',
              'https://i.imgur.com/uY2PCm2_d.webp?maxwidth=760&fidelity=grand'

          ],
          description: 'A-Zoom Manager is a useful extension for students and professionals to save time and energy while using Zoom, including the ability to store meeting info and passwords and categorize meetings by type. Other features include: <p>● storing zoom passwords<br> <p>● click to join feature and automatically copying password to clipboard<br> <p>● a beautiful dark theme<br>',
          link: 'https://chrome.google.com/webstore/detail/a-zoom-manager/fbeielocoeimhniadlepcooihbbgaplf'
        },
        {
          id: 3,
          title: 'NoteTask',
          src: 'https://i.imgur.com/tyxkzIu_d.webp?maxwidth=760&fidelity=grand',
          pictures: [
            'https://i.imgur.com/MTLlB0z.png',
            'https://i.imgur.com/JeQOY7G_d.webp?maxwidth=760&fidelity=grand',
            'https://i.imgur.com/pQEdh0G_d.webp?maxwidth=760&fidelity=grand',
            'https://i.imgur.com/zeYxWsu_d.webp?maxwidth=760&fidelity=grand'

          ],
          description: 'As someone who always has an idea for tasks I would like to do later such as grocery shopping or a coding project. I usually enter the ideas or whatever I need into a notetaking app, but it get’s messy with the other notes. NoteTask solves this through a notepad complete with a calendar view and reminder and sub-task function<br>  ',
          link: 'https://github.com/huzailhassan/NoteTask'
        },
      ],
      dialog: false,
      currentItem: false,
      page: 0
    };
  },
  methods: {
    openDialog(item) {
      console.log('item', item)
      this.currentItem = item
      this.dialog = true
    },
    openLink(link) {
      window.open(link)
    }
  }
};
</script>