<template>
    <form @submit.prevent="registrarProyecto">
      <div class="mb-3">
        <label  class="form-label">Proyecto</label>
        <input type="text" class="form-control" required/>
      </div>

      <div class="mb-3">
        <label class="form-label">Actividad</label>
        <select class="form-select "  required>
            <option disabled selected>Seleccione tipo de actividad ...</option>
            <option >Aplicaciones Web con Vue.js</option>
            <option >Backend Service con Node.js</option>
            <option >App Movil con Reacy Native</option>
        </select>
      </div>

      <div class="mb-3">
        <label  class="form-label">urgente</label>
        <input type="checkbox" class="form-check-input">
      </div>


      <button type="submit" class="btn btn-primary">Guardar</button>
    </form>

    
</template>
<script>
    export default {
    data: () => ({
        
    }),
    methods: {
        registrarProyecto() {
            console.log("Proyecto Registrado...");
        },
    },
    };
</script>