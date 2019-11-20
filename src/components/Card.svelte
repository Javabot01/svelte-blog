<script>
  export let url, title, desc, date;
</script>

<!-- Card -->
<!-- Card -->

<div class="card">
  <div class="card-body">
    <div class="row">
      <div class="col-md-7">
        <h6 class="card-title">{title}</h6>
        <h6 class="card-subtitle mb-2 text-muted">{date}</h6>
        <p class="card-text">{desc}</p>
        <a href="#!" class="card-link">Read More</a>
      </div>
      <div class="col-md-4">
        <div class="card-img-div">
          <img class="card-img-top" src={url} alt={title} />
        </div>
      </div>
    </div>
  </div>
</div>
