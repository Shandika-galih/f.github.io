<template>
    <div class="py-4 container-fluid">
    <div class=" row">
        <div class="col-12">
        <tampil-tugas/>
        </div>
        <div class="mt-4 row">
        <div class="col-12">
            <projects-table />
        </div>
        </div>
    </div>
    </div>
</template>

<script>
import TampilTugas from "./components/TampilTugas.vue";
import ProjectsTable from "./components/ProjectsTable.vue";
export default {
    name: "tugas",
    components: {
    TampilTugas,
    ProjectsTable
    },
};
</script>