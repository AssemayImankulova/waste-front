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

export default {
    name:'NewSite',
}

</script>

<style>
.createPage{
    width: 40%;
    margin: auto;
}
</style>
