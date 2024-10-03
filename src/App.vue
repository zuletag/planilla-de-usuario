<script>
export default {
  name: "App",
  data() {
    return {
      usuario: {
        nombre: "",
        nacionalidad: "",
        genero: "",
        direccion: "",
        ecivil: "",
        continentes: [],
      },
    };
  },
};
</script>

<template>
  <!-- Formulario -->
  <div id="formStyle">
    <form>
      <div class="mb-3">
        <label class="form-label">Nombre</label>
        <input class="form-control" v-model="usuario.nombre" />
      </div>
      <div class="mb-3">
        <label class="form-label">Nacionalidad</label>
        <select class="form-select" v-model="usuario.nacionalidad">
          <option value="Chile">Chile</option>
          <option value="Extranjero">Extranjero</option>
        </select>
      </div>
      <div class="mb-3">
        <label class="form-label">Genero</label>
        <div class="d-flex gap-3">
          <div class="form-check">
            <input class="form-check-input" type="radio" name="flexRadioDefault" id="m" value="M"
              v-model="usuario.genero" />
            <label class="form-check-label fw-normal" for="M"> Masculino </label>
          </div>
          <div class="form-check">
            <input class="form-check-input" type="radio" name="flexRadioDefault" id="f" value="F"
              v-model="usuario.genero" />
            <label class="form-check-label fw-normal" for="F"> Femenino </label>
          </div>
        </div>
      </div>
      <div class="mb-3">
        <label class="form-label">Dirección </label>
        <input class="form-control" v-model="usuario.direccion" />
      </div>
      <div class="mb-3">
        <label class="form-label">Estado Civil</label>
        <div class="d-flex gap-3">
          <div class="form-check">
            <input class="form-check-input" type="radio" name="flexRadioDefault" id="soltero" value="Soltero"
              v-model="usuario.ecivil" />
            <label class="form-check-label fw-normal" for="M"> Soltero </label>
          </div>
          <div class="form-check">
            <input class="form-check-input" type="radio" name="flexRadioDefault" id="casado" value="Casado"
              v-model="usuario.ecivil" />
            <label class="form-check-label fw-normal" for="F"> Casado </label>
          </div>
        </div>
      </div>
      <div class="mb-3">
        <label class="form-label">Continentes que ha visitado </label>
        <div>
          <div class="form-check form-check-inline">
            <input v-model="usuario.continentes" class="form-check-input" type="checkbox" id="inlineCheckbox1" value="Ámerica">
            <label class="form-check-label" for="inlineCheckbox1">Ámerica</label>
          </div>
          <div class="form-check form-check-inline">
            <input v-model="usuario.continentes" class="form-check-input" type="checkbox" id="inlineCheckbox2" value="Europa">
            <label class="form-check-label" for="inlineCheckbox2">Europa</label>
          </div>
          <div class="form-check form-check-inline">
            <input v-model="usuario.continentes" class="form-check-input" type="checkbox" id="inlineCheckbox3" value="Asia">
            <label class="form-check-label" for="inlineCheckbox2">Asia</label>
          </div>
          <div class="form-check form-check-inline">
            <input v-model="usuario.continentes" class="form-check-input" type="checkbox" id="inlineCheckbox4" value="África">
            <label class="form-check-label" for="inlineCheckbox2">África</label>
          </div>
          <div class="form-check form-check-inline">
            <input v-model="usuario.continentes" class="form-check-input" type="checkbox" id="inlineCheckbox5" value="Oceania">
            <label class="form-check-label" for="inlineCheckbox2">Oceania</label>
          </div>
        </div>
      </div>
    </form>
  </div>

  <!-- Planilla -->
  <div id="planilla">
    <div class="planilla text-center mt-5 w-75 mx-auto">
      <h1>Planilla de Usuario</h1>
      <hr />
      <table class="table table-striped">
        <thead>
          <tr>
            <th>Nombre</th>
            <th>Nacionalidad</th>
            <th>Género</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>{{ usuario.nombre }}</td>
            <td>{{ usuario.nacionalidad }}</td>
            <td>{{ usuario.genero }}</td>
          </tr>
        </tbody>
      </table>
      <table class="table table-striped">
        <thead>
          <tr>
            <th>Dirección de residencia</th>
            <th>Estado civil</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>{{ usuario.direccion }}</td>
            <td>{{ usuario.ecivil }}</td>
          </tr>
        </tbody>
      </table>
      <table class="table table-striped">
        <thead>
          <tr>
            <th>Continentes que ha visitado</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>{{ usuario.continentes.join (", ") }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<style scoped>
#formStyle {
  display: block;
  margin: 40px;
  padding: 60px;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #f9f9f9;
}

.form-label {
  font-weight: bold;
}
</style>
