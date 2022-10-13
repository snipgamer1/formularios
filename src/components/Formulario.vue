<template>
    <div class="row">
        <div class="col-12 col-md-4">
            <ProgressBar />

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

        </div>
        <div class="col-12 col-md-8">
            <total-proyectos 
            :numeroProyectos="numeroProyectos" 
            :proyectos="proyectos" 
            :cambiarEstado="cambiarEstado" />
        </div>
    </div>

    
</template>

<script>
    
    import TotalProyectos from "./TotalProyectos.vue";
    import ProgressBar from "./ProgressBar.vue";
    export default {
    data: () => ({
        proyecto: "",
        tipo: "",
        urgente: false,
        proyectos: [],
    }),
    methods: {
        registrarProyecto() {
            const proyecto ={
                proyecto: this.proyecto,
                tipo: this.tipo,
                urgente: this.urgente,
            };
            this.proyectos.push(proyecto);
            this.proyecto = "";
            this.tipo =  "";
            this.urgente = false;
        },
        cambiarEstado(id) {
            this.proyectos[id].urgente = !this.proyectos[id].urgente;
        }
    },
    computed: {
        numeroProyectos() {
            return this.proyecto.length;
        }
        
    },
    components: { TotalProyectos, ProgressBar }
    
};
</script>