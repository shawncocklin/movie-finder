<script context="module">
  export async function load({ fetch, params }) {
    const response = await fetch(`https://api.themoviedb.org/3/movie/${params.id}?api_key=afcb2637b8135fc61cfd841909ce5b5a&language=en-US`)
    const movieDetail = await response.json()
    // console.log(data)
    if(response.ok) {
      return {
        props: { movieDetail }
      }
    }
  }
</script>

<script>
  export let movieDetail
</script>

<div class="movie-details">
  <div class="image-container">
    <img src={`https://image.tmdb.org/t/p/original${movieDetail.backdrop_path}`} alt={movieDetail.title}>
  </div>
  <div class="text-container">
    <h1>{movieDetail.title}</h1>
    <p class="overview">{movieDetail.overview}</p>
    <p>
      <span>Release Date: </span>{movieDetail.release_date} <br>
      <span>Rating: </span>{movieDetail.vote_average} <br>
      <span>Runtime: </span>{movieDetail.runtime}mins
    </p>
  </div>
</div>

<style>
  h1 {
    padding: 1rem 0 2rem;
  }

  p {
    padding: 1rem 0;
  }

  .image-container {
    width: 100%;
  }
  img {
    width: 100%;
    border-radius: 1rem;
  }

  .movie-details {
    margin: 2rem 20%;
  }

  span {
    font-weight: bold;
  }
</style>