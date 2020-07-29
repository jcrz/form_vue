<template>
  <div class="container shadow-sm p-4 bg-white rounded">
    <br />
    <section class="row">
      <div class="col-md-12">
        <h2 class="text-center">Encuesta de Satisfacción.</h2>
        <p class="text-center">Curso Desarrollador de Aplicaciones Front-End.</p>
      </div>
    </section>
    <hr />
    <br />
    <section class="row">
      <section class="col-md-12">
        <h4>Datos básicos</h4>
        <p></p>
      </section>
    </section>
    <section class="row">
      <section class="col-md-12">
        <!-- Tú Nombre -->
        <section class="row">
          <div class="col-md-4">
            <label for="nombre">Tú Nombre:</label>
          </div>
          <div class="col-md-8">
            <input class="form-control" type="text" id="nombre" v-model="nombre" required />
          </div>
        </section>
        <!-- Locación Dojo -->
        <section class="row">
          <div class="col-md-4">
            <label for="locacion">Locación Dojo:</label>
          </div>
          <div class="col-md-8">
            <select class="form-control" id="locacion" v-model="locacion" required>
              <option value="Temuco">Temuco</option>
              <option value="Santiago">Santiago</option>
            </select>
          </div>
        </section>
        <!-- Lenguaje Favorito -->
        <section class="row">
          <div class="col-md-4">
            <label for="lenguaje">Lenguaje Favorito:</label>
          </div>
          <div class="col-md-8">
            <select class="form-control" id="lenguaje" v-model="lenguaje" required>
              <option value="JavaScript">JavaScript</option>
              <option value="Python">Python</option>
              <option value="Java">Java</option>
              <option value="PHP">PHP</option>
              <option value="Ruby">Ruby</option>
            </select>
          </div>
        </section>
        <hr />
        <!-- Curso -->
        <section class="row">
          <div class="col-md-12">
            <h4>Curso.</h4>
            <p></p>
          </div>
        </section>
        <!-- Pregunta -->
        <section class="row">
          <div class="col-md-6">
            <p for="nombre">¿Recomendaría el curso a sus familiares y amigos?</p>
          </div>
          <div class="col-md-2">
            <label class="radio">
              <input type="radio" v-model="respuestaP" name="pregunta1" id="pregunta1" value="Si" /> Si
            </label>
          </div>
          <div class="col-md-2">
            <label class="radio">
              <input type="radio" v-model="respuestaP" name="pregunta1" id="pregunta1" value="No" /> No
            </label>
          </div>
          <div class="col-md-2">
            <label class="radio">
              <input
                type="radio"
                v-model="respuestaP"
                name="pregunta1"
                id="pregunta1"
                value="Tal vez"
              /> Tal vez
            </label>
          </div>
        </section>
        <hr />
        <!-- Comentario -->
        <section class="row">
          <div class="col-md-12">
            <h3>Comentarios.</h3>
            <p></p>
          </div>
        </section>
        <section class="row">
          <div class="col-md-12">
            <div class="form-group">
              <label for="comment">Comentarios:</label>
              <textarea
                class="form-control"
                rows="3"
                id="comentarios"
                v-model="comentario"
                required
              ></textarea>
            </div>
          </div>
        </section>
        <!-- Botones -->
        <section class="row">
          <div class="col-md-12">
            <button
              @click="alerta()"
              type="button"
              class="btn btn-info"
              id="saveForm"
              onclick="saveForm"
            >Guardar Encuesta</button>
          </div>
        </section>
      </section>
    </section>
    <br />
    <br />
    <footer>
      <p>Todos los derechos reservados para Inforcap.</p>
    </footer>
  </div>
</template>

<script>
export default {
  name: "Formulario",
  data: function() {
    return {
      nombre: "",
      locacion: null,
      lenguaje: null,
      respuestaP: null,
      comentario: ""
    };
  },
  methods: {
    alerta() {
      this.$swal({
        title: '<h5>Datos ingresados correctamente</h5>',
        icon: 'success',
        html: `Nombre: ${this.nombre}` + '<br />' + 
              `Locación: ${this.locacion}` + '<br />' +
              `Lenguaje: ${this.lenguaje}` + '<br />' +
              `Respuesta: ${this.respuestaP}` + '<br />' +
              `Comentario: ${this.comentario}` + '<br />'
      });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  max-width: 600px;
}
input {
  width: 100%;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
