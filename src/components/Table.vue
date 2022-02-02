<template>
<div class="div-main">
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
            Categoria
          </th>
          <th class="text-columms">
            Duração
          </th>
          <th class="text-columms">
            Nível
          </th>
          <th class="text-columms">
            Valor
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
          <td class="textLines">{{ item.category }}</td>
          <td class="textLines">{{ item.duration }}</td>
          <td class="textLines">{{ item.nivel }}</td>
          <td class="textLines">{{ item.price }}</td>
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
  
</div>
</template>

<script>
import axios from 'axios';

export default {
    created () {
    axios
      .get('http://localhost:8080/api/courses')
      .then(response => this.items = response.data)
  },
  data: () => ({
    items: []
  }),
}
</script>

<style>
.div-main {
  padding-left: 5%;
  padding-right: 5%;
}

.text-columms {
  align-content: center;
  text-align: center;
  padding-left: 20%;
}

</style>
