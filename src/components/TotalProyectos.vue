<template>
    <div class="row my-3">
        <div class="col-6">
            <h3>Total de proyectos: {{ numerosProyectos}}</h3>
        </div>
        <div class="col-6 text-end">
            <button @click="limpiarData" class="btn btn-warning">Limpiar</button>
        </div>


    </div>
    <div class="table-responsive">
        <table class="table table-dark table-hover">
            <thead>
                <tr>
                    <th scope="col">#</th>
                    <th scope="col">Proyecto</th>
                    <th scope="col">Tipo</th>
                    <th scope="col">Urgente</th>
                    <th scope="col">Completado</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(proyecto, index) in proyectos">
                    <td scope="row">{{ index + 1}}</td>
                    <td>{{ proyecto.proyecto}}</td>
                    <td>{{ proyecto.tipo}}</td>
                    <td @click="cambiarEstado(proyecto, 'urgente')" :class="proyecto.urgente ? 'bg-success' : 'bg-danger'">{{ proyecto.urgente ? "Si" : "No"}}</td>
                    <td @click="cambiarEstado(proyecto, 'completado')" :class="proyecto.completado ? 'bg-success' : 'bg-danger'">{{ proyecto.completado ? "Completo" : "Incompleto"}}</td>
                </tr>
                
            </tbody>
        </table>
    </div>
    
</template>

<script>
    export default {
        props: ['numeroProyecto', 'proyectos', 'cambiarEstado', 'limpiarData']
    };

</script>