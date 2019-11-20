<script>
  //Modules
  import axios from "axios";
  import moment from "moment";
  import articleStore from "../stores/articles.js"
  //Components
  import Card from "../components/Card.svelte";
  import Loader from "../components/Loader.svelte";

  let articles;

  let key = "c9af8f0c28414c9fbee04ece130f1447";
  let country = "us";

  let url = `https://newsapi.org/v2/top-headlines?country=${country}&apiKey=${key}`;

  (async function getNews() {
    try {
      const res = await axios.get(url);
      articles = res.data.articles;
    } catch (error) {
      console.error(error);
    }
  })();

  function truncate(text, len) {
    if (text.length > 92) return `${text.substring(0, len)}...`;
    return text;
  }
</script>

<div class="container">
  <div class="row">
    {#if !articles}
      <Loader />
    {:else}
      {#each articles as article, i}
        <div class="col-md-12 mt-3">
          <Card
            url={article.urlToImage}
            title={truncate(article.title, 92)}
            desc={article.description ? article.description : '...'}
            date={moment().calendar(article.publishedAt)} />
        </div>
      {/each}
    {/if}

  </div>
</div>
