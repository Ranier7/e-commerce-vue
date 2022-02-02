<template>
  <v-app>
    <v-app-bar class="app-bar" app color="primary" dark>
      <div class="div-title">
        <strong>MINI E-COMMERCE</strong>
      </div>
      <div class="div-cart">
        <v-btn
          text
          @click="dialog=true"
        >
          <v-icon>mdi-cart</v-icon>
        </v-btn>
        <Dialog :dialog.sync="dialog" />
      </div>   
    </v-app-bar>
    <v-main>
      <div class="div-toolbar">
        <v-toolbar
          color="blue"
          dense
          elevation="15"
          rounded
        >
        <v-toolbar-title class="titleCatalogo">Catálogo de Cursos</v-toolbar-title>
        
        </v-toolbar>
      </div>
      
      <Table></Table>
    </v-main>
    <Footer></Footer>
  </v-app>
</template>

<script>
import Dialog from './components/Dialog';
import Footer from './components/Footer';
import Table from './components/Table';

export default {
  name: 'App',

  components: {
    'Table': Table,
    'Footer': Footer,
    'Dialog': Dialog
  },

  data: () => ({
    listItems: [],
    dialog: false
  }),
  
};
</script>

<style>

.div-cart {
  position: absolute;
  right: 0;
}

.div-toolbar {
  padding-top: 2.5%;
  padding-left: 5%;
  padding-right: 5%;
}

.title-toolbar {
  color: white;
}

.titleCatalogo {
  color: white;
  display: flex;
  justify-content: center;
  width: 100%;
}
</style>
