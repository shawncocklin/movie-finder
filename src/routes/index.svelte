<script context="module">
   export async function load({fetch}) {
     const response = await fetch(`https://api.themoviedb.org/3/movie/popular?api_key=afcb2637b8135fc61cfd841909ce5b5a&language=en-US&page=1`)
     const data = await response.json()
    //  console.log(data)
     if(response.ok) {
       return {
         props: { popular: data.results }
       }
     }
   }
</script>

<script>
  import PopularMovies from '../components/PopularMovies.svelte'
  import SearchMovies from '../components/SearchMovies.svelte'
  export let popular
  
</script>

<section>
  <SearchMovies/>
  <PopularMovies movies={ popular }/>
</section>

<style>
  
</style>