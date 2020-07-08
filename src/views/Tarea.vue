<template>
  <v-container grid-list-xl>
    <v-layout row wrap>
      <v-flex md6>
        <v-card class="mb-3" v-for="(item, index) in listaTareas" :key="index">
          <v-card-text>
            <v-chip class="ml-0" color="pink" label text-color="white">
              <v-icon left>label</v-icon>
              {{item.titulo}}
            </v-chip>
            <p>{{item.descripcion}}</p>
            <v-btn color="warning" class="ml-0" @click="editarTarea(index)">Editar</v-btn>
            <v-btn color="error" class="ml-2" @click="eliminarTarea(item.id)">Eliminar</v-btn>
          </v-card-text>
        </v-card>
      </v-flex>
      <v-flex md6>
        <v-card class="mb-3 pa-3">
          <v-form @submit.prevent="agregarTareas" v-if="formaAgregar">
            <v-text-field label="Titulo de la tarea" v-model="titulo"></v-text-field>
            <v-textarea label="Descripcion de tarea" v-model="descripcion"></v-textarea>
            <v-btn v-if="formaAgregar" block color="success" type="submit">Agregar Tarea</v-btn>
            <v-btn
              v-if="!formaAgregar"
              block
              color="warning"
              type="button"
              @click="editar"
            >Editar Tarea</v-btn>
          </v-form>
          <v-form @submit.prevent="editar" v-if="!formaAgregar">
            <v-text-field label="Titulo de la tarea" v-model="titulo"></v-text-field>
            <v-textarea label="Descripcion de tarea" v-model="descripcion"></v-textarea>
            <v-btn
              block
              color="warning"
              type="submit"
            >Editar Tarea</v-btn>
          </v-form>
        </v-card>
      </v-flex>
    </v-layout>
    <v-snackbar v-model="snackbar">
      {{ mensaje }}
      <template v-slot:action="{ attrs }">
        <v-btn dark color="pink" text v-bind="attrs" @click="snackbar = false">Cerrar</v-btn>
      </template>
    </v-snackbar>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      listaTareas: [
        {
          id: 1,
          titulo: "Título #1",
          descripcion:
            ">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Molestiae magni recusandae possimus iusto! Delectus eaque sint odit ut? Illum iure perferendis ipsam accusamus labore velit, vel optio laudantium at molestias"
        },
        {
          id: 2,
          titulo: "Título #2",
          descripcion:
            ">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Molestiae magni recusandae possimus iusto! Delectus eaque sint odit ut? Illum iure perferendis ipsam accusamus labore velit, vel optio laudantium at molestias"
        }
      ],
      titulo: "",
      descripcion: "",
      snackbar: false,
      mensaje: "",
      formaAgregar: true,
      indexTarea: ""
    };
  },
  methods: {
    agregarTareas() {
      if (this.titulo === "" || this.descripcion === "") {
        this.snackbar = true;
        this.mensaje = "Por favor rellena todos los campos";
      } else {
        this.listaTareas.push({
          id: Date.now(),
          titulo: this.titulo,
          descripcion: this.descripcion
        });
        this.titulo = "";
        this.descripcion = "";
        this.snackbar = true;
        this.mensaje = "Tarea agregada";
      }
    },
    eliminarTarea(id) {
      this.listaTareas = this.listaTareas.filter(e => e.id != id);
    },
    editarTarea(index) {
      this.formaAgregar = false;
      this.titulo = this.listaTareas[index].titulo;
      this.descripcion = this.listaTareas[index].descripcion;
      this.indexTarea = index;
    },
    editar() {
      this.listaTareas[this.indexTarea].titulo = this.titulo;
      this.listaTareas[this.indexTarea].descripcion = this.descripcion;
      this.formaAgregar = true;
      this.titulo = '';
      this.descripcion = '';
      this.snackbar = true;
      this.mensaje = "Tarea actualizada";
    }
  }
};
</script>
