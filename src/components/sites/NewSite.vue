<template>
    <div class="createPage">
        <h1>CreatePage</h1>
       <form>
        <div class="form-group">
            <label>siteName</label>
            <input  class="form-control"  placeholder="Mangystau">
        </div>
        <div class="form-group">
            <label>siteComments</label>
            <textarea class="form-control" rows="3" placeholder="Desert area"></textarea>
        </div>
       </form>
       <button class="btn btn-outline-primary">Create</button>
    </div>
</template>

<script>
// import gql from "graphql-tag"
// const AllPosts=gql`query (
//     $options: PageQueryOptions
//   ) {
//     posts(options: $options) {
//       data {
//         id
//         title
//         body
//       }
//     }
//   }`
export default {
    name:'NewSite',
    methods:{
  //    async addNewPost(){
  //         this.isLoading=true;
  //         const result = await this.$apollo
  //         .mutate ({
  //           mutation: gql`mutation (
  //             $input: CreatePostInput!
  //           ) {
  //             createPost(input: $input) {
  //               id
  //               title
  //               body
  //             }
  //           }`,
  //           variables: {
  //             input:{
  //               title: this.newPost.title,
  //               body: this.newPost.body
  //             }
  //           },
  //            update: (store, { data: { createPost } }) => {
  //           // // Read the data from our cache for this query.
  //            const data = store.readQuery({ query: AllPosts })
  //           // // Add our tag from the mutation to the end
  //             data.posts.data.push(createPost)
  //           // // Write our data back to the cache.
  //             store.writeQuery({ query:AllPosts, data })
  //          }  

  //         })
  //         //  this.isLoading=true;
  //           .then( response => {
  //              this.isLoading=false;
  //             this.$router.push("/sites");
  //              console.log(response)
  //           })


  //          console.log("Data:", result);

  //      },
     }

}

</script>

<style>
.createPage{
    width: 40%;
    margin: auto;
}
</style>
