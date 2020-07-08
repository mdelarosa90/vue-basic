<template>
  <v-container grid-list-md>
    <v-layout row wrap>
      <v-flex xs12 sm6>
        <v-card>
          <v-img src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"></v-img>
          <v-card-title>
            <h2>Lorem, ipsum dolor</h2>
          </v-card-title>
          <v-card-text>Lorem ipsum dolor sit amet consectetur adipisicing elit. Tenetur hic temporibus reiciendis eum nam molestiae, natus, ea architecto perspiciatis veniam nulla nobis asperiores! Exercitationem praesentium voluptatibus, atque ipsa numquam deleniti!</v-card-text>
          <v-card-actions>
            <v-btn color="info" text>Accción</v-btn>
          </v-card-actions>
        </v-card>
      </v-flex>
      <v-flex xs12 sm6>
        <v-card>
          <v-img src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg">
            <v-container>
              <v-layout>
                <v-flex>
                  <span class="headline white--text">Lorem, Ipsum Dolor</span>
                </v-flex>
              </v-layout>
            </v-container>
          </v-img>
          <v-card-title>
            <h2>Lorem, ipsum dolor</h2>
          </v-card-title>
          <v-card-text>Lorem ipsum dolor sit amet consectetur adipisicing elit. Tenetur hic temporibus reiciendis eum nam molestiae, natus, ea architecto perspiciatis veniam nulla nobis asperiores! Exercitationem praesentium voluptatibus, atque ipsa numquam deleniti!</v-card-text>
          <v-card-actions>
            <v-btn color="info" text @click="dialog = true">Accción</v-btn>
          </v-card-actions>
        </v-card>
      </v-flex>
    </v-layout>
    <!--Dialog-->
    <v-dialog v-model="dialog" width="500" persistent>
      <v-card>
        <v-card-title>Este es el titulo</v-card-title>
        <v-card-text>Lorem ipsum dolor sit amet consectetur adipisicing elit. Hic quae voluptate repellendus amet eius officiis cum inventore obcaecati iste, error perferendis aut animi cumque illum ullam sunt. Enim, voluptatum facilis?</v-card-text>
        <v-divider></v-divider>
        <v-card-action>
          <v-btn @click="dialog = false">Cerrar</v-btn>
        </v-card-action>
      </v-card>
    </v-dialog>
  </v-container>
</template>

<script>
// @ is an alias to /src

export default {
  data() {
    return {
      dialog: false
    }
  },
};
</script>