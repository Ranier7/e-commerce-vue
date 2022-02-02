<template>
  <div class="text-center">
    <v-dialog
      v-model="dialog"
      width="500"
    >
      <v-card>
        <v-card-title class="text-h5 grey lighten-2">
          Privacy Policy
        </v-card-title>

        <v-card
  elevation="15"
  >
  <v-simple-table class="table">
    <template v-slot:default>
      <thead>
        <tr>
          <th class="text-columms">
            Produto
          </th>
          <th class="text-columms">
            Ações
          </th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="item in items"
          :key="item._id"
        >
          <td class="textLines">{{ item.name }}</td>
          <td> 
            <v-btn
              class="mx-2"
              fab
              dark
              small
              color="blue"
            >
              <v-icon dark>
                mdi-plus
              </v-icon>
            </v-btn>
          </td>
        </tr>
      </tbody>
    </template>
  </v-simple-table>  
  </v-card>

        <v-divider></v-divider>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            color="primary"
            text
            @click="dialog = false"
          >
            I accept
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
export default {
    props: {
        dialog: {
        default: false
      }
    },
    methods: {
        close() {
        this.childValue = false;
      }
    },
    data() {
        return {
        childValue: this.default // initialize props value
  }
}
}
</script>

<style>

</style>