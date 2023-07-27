<script>
    export let animeList;
    import { Deta } from "deta";

    const deta = Deta("project_key");
    const db = deta.Base("Data");

    let o = {
        key: 1,
        name: ""
    }

    async function asdf() {
        let result = await db.put(o);
    }
</script>

<div class="anime-list">
    {#each animeList as anime}
        <div class="anime-card">
            <img src={anime.image} alt={anime.title} />
            <h2>{anime.title}</h2>
            <p>Rating: {anime.rating}</p>
        </div>
    {/each}
</div>

<style>
    .anime-list {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
        gap: 20px;
        justify-content: center;
        align-items: center;
    }
  
    .anime-card {
        border: 1px solid #ccc;
        padding: 10px;
        border-radius: 8px;
        text-align: center;
    }
  
    .anime-card img {
        width: 200px;
        height: 250px;
        object-fit: cover;
        border-radius: 8px;
    }
</style>