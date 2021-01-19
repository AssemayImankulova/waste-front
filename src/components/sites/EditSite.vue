<template>
  <div class="editPage">
      <h1>Edit Page</h1>
      <form>
        <div class="form-group">
            <label>siteName</label>
            <input  class="form-control"  placeholder="enter siteName">
        </div>
        <div class="form-group">
            <label>siteComments</label>
            <textarea class="form-control" rows="3" placeholder="enter siteComments"></textarea>
        </div>
       </form>
       <button class="btn btn-outline-primary">Edit</button>
  </div>
</template>

<script>
export default {
  name:'EditSite'
}
</script>

<style>
.editPage{
    width: 40%;
    margin: auto;
}
</style>
