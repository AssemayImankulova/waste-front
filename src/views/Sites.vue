<template>
  <div>
    <vue-good-table
      :columns="columns"
      :rows="sites"
      :line-numbers="true"
      :search-options="{
        enabled: true,
        placeholder: 'Введите текст для поиска',
      }"
      :pagination-options="paginationOptions"
      compactMode
      >

      <div slot="table-actions">
        <router-link :to="{path:'/new-site/'}"><button class="btn btn-outline-primary">Create</button></router-link>
        <button class="btn btn-outline-primary" ><i class="fa fa-download"></i></button>
      </div>

       <template slot="table-row" slot-scope="props">
        <span v-if="props.column.field == 'action'">
          <router-link to="/edit-site">
            <button class="btn-primary btn-small btn">
              <i class="fa fa-edit"></i>
            </button>
          </router-link>
          <router-link to="/show-site">
            <button class="btn-info btn-small btn">
              <i class="fa fa-eye"></i>
            </button>
          </router-link>
          <button class="btn-danger btn-small btn">
            <i class="fa fa-trash"></i>
          </button>
        </span>
      </template>

    </vue-good-table>
  </div>
</template>

<script>
import 'vue-good-table/dist/vue-good-table.css'
import { VueGoodTable } from 'vue-good-table';
// import gql from "graphql-tag"
// const AllPosts = gql`
//   query (
//     $options: PageQueryOptions
//   ) {
//     posts(options: $options) {
//       data {
//         id
//         title
//         body
//       }
//     }
//   }
// `
export default {
  name: 'Sites',
  components: {
    VueGoodTable,
  },
  data(){
    return{
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
      sites: [
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
      // deletePostMutation:`mutation ($id: ID!) 
      //   {
      //     deletePost(id: $id)
      //   }` 
     }
  },
  // apollo:{
  //   posts:{
  //     query: AllPosts,
  //   }
  // },
  // methods:{
  //    deletePost(id) {
  //     console.log(id)
  //     this.$apollo.mutate({
  //       mutation: gql`${this.deletePostMutation}`,
  //       variables: {
  //         id: id,
  //       },
  //       update: (store) => {
  //         const queries = [
  //           { query: AllPosts },
  //           { query: AllPosts, variables: { filter: { done: this.post } } },
  //         ]
  //         const data = queries.map(query => store.readQuery(query))
  //         data.forEach(({ posts: list }) => {
  //           console.log(list)
  //           const index = list.data.findIndex(o => o.id === id)
  //           if (index !== -1) {
  //             list.data.splice(index, 1)
  //           }
  //         })
  //         queries.forEach((query, index) => {
  //           store.writeQuery({
  //             ...query,
  //             data: data[index],
  //           })
  //         })
  //       },
  //     });  
     
  //   }
  // }
}
</script>
