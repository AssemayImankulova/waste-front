<template>
  <div class="main-content-container container-fluid px-4">
    <div class="page-header row no-gutters py-4">
      <div class="col-12 col-sm-4 text-center text-sm-left mb-0">
        <span class="text-uppercase page-subtitle">
          Список участков
        </span>
        <h3 class="page-title">Участки:</h3>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <div class="card card-small mb-4">
          <div class="card-body">
            <SitesTable />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import SitesTable from '@/components/sites/SitesTable';

export default {
  components: {
    SitesTable,
  },
};
</script>

<style scoped>

</style>
