<script>
  import {createEventDispatcher} from "svelte"
  const dispatch = createEventDispatcher();
  export let searchTerm
</script>

<div class="row justify-content-center my-2">
  <div class="col-12 col-lg-6 border rounded bg-light p-3">
    <h4 class="mb-1">
      Search:
      <small>
        {#if searchTerm}
          for
        {/if}
        {searchTerm}
      </small>
    </h4>
    <div class="input-group">
      <input type="text"
             aria-label="Search Input"
             class="form-control"
             bind:value={searchTerm}
             on:keyup={() => {
               dispatch('updateSearch')
             }}>
    </div>
  </div>

</div>


