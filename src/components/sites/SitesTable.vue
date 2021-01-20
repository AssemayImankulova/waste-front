<template>
  <div class="meta-table">
    <vue-good-table
        :columns="columns"
        :rows="rows"
        styleClass="vgt-table condensed striped"
        :search-options="{
        enabled: true,
        placeholder: 'Введите текст для поиска',
      }"
        :pagination-options="paginationOptions"
    >
      <div slot="table-actions">
        <router-link to="/new-site">
          <button type="button" class="btn btn-primary btn-sm mr-2">
            + Новый участок
          </button>
        </router-link>

        <button
            class="btn btn-primary btn-sm mr-2"
        >
          <i class="fa fa-download"></i>
        </button>

      </div>
      <template slot="table-row" slot-scope="props">
        <span v-if="props.column.field == 'action'">
          <router-link to="/edit-site">
            <button class="btn-primary btn-small btn mr-2">
              <i class="fa fa-edit"></i>
            </button>
          </router-link>
          <router-link to="/show-site">
            <button class="btn-info btn-small btn mr-2">
              <i class="fa fa-eye"></i>
            </button>
          </router-link>
          <button class="btn-danger btn-small btn mr-2">
            <i class="fa fa-trash"></i>
          </button>
        </span>
      </template>
    </vue-good-table>
  </div>
</template>

<script>
import 'vue-good-table/dist/vue-good-table.css';
import { VueGoodTable } from 'vue-good-table';

export default {
  name: 'SitesTable',
  data() {
    return {
      columns:[
        {
          label: 'SiteName',
          field: 'siteName',
        },
        {
          label: 'SiteComments',
          field: 'siteComments',
        },
        {
          label: 'Action',
          field: 'action',
        },
      ],
      rows: [
        {
          id: 1,
          siteName: 'Kazakhstan',
          siteComments: 'qwertyuiop'
        },
        {
          id: 2,
          siteName: 'Russia',
          siteComments: 'qwertyuiop'
        },
        {
          id: 3,
          siteName: 'USA',
          siteComments: 'qwertyuiop'
        }
      ],
      paginationOptions: {
        enabled: true,
        mode: 'pages',
        perPage: 5,
        position: 'bottom',
        perPageDropdown: [5, 10, 20],
        dropdownAllowAll: false,
        setCurrentPage: 1,
        nextLabel: '>',
        prevLabel: '<',
        rowsPerPageLabel: 'Строк на странице',
        ofLabel: '/',
        pageLabel: 'стр.', // for 'pages' mode
        allLabel: 'Все',
      },
    }
  },
  components: {
    VueGoodTable,
  },
}
</script>

<style scoped>

</style>
