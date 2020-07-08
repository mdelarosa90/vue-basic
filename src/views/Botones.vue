<template>
  <v-container>
    <v-layout>
      <v-flex>
        <v-btn>Texto</v-btn>
        <v-btn color="primary">Texto</v-btn>
        <v-btn color="blue" dark>Texto</v-btn>
        <v-btn color="secondary" text>Sin Fondo</v-btn>
        <v-btn color="warning" large>Sin Fondo</v-btn>
        <v-btn color="warning" small disabled>Sin Fondo</v-btn>
        <v-btn color="info" depressed>Sin Fondo</v-btn>

        <v-btn dark color="pink">
          <v-icon>favorite</v-icon>
        </v-btn>
        <v-btn dark color="pink" fab small>
          <v-icon>forum</v-icon>
        </v-btn>
        <v-btn color="success">
          texto
          <v-icon>forum</v-icon>
        </v-btn>
        <v-btn color="success">
          texto
          <v-icon class="ml-2">forum</v-icon>
        </v-btn>
        <v-btn color="success" outlined>
          texto
          <v-icon right>forum</v-icon>
        </v-btn>
        <v-btn color="success" outlined block>
          <v-icon left>forum</v-icon>texto
        </v-btn>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
// @ is an alias to /src

export default {
  data() {
    return {};
  }
};
</script>