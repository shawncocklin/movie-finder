<script>
  let inputValue = ''
</script>

<form class="search">
  <label for="query">Search Movie</label>
  <input bind:value={inputValue} type="text" name="query" id="query">
  <button>Search</button>
</form>