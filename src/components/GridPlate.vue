<template>
  <section class="grid-container">
    <section class="grid-left">
      <div class="article">
        <article>add content here</article>
      </div>
      <div class="article">
        <article>add content here</article>
      </div>
      <!-- <div class="article">
        <article>add content here</article>
      </div> -->
    </section>
    <section class="grid-right">
      <div class="article">
        <article>add content here</article>
      </div>
      <div class="article">
        <article>add content here</article>
      </div>
      <!-- <div class="article">
        <article>add content here</article>
      </div> -->
    </section>
  </section>
</template>

<script>
export default {
  name: "GridPlate",
};
</script>

<style lang="scss">
.grid-container {
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  height: 100vh;

  .article {
    background-color: #14213d;
    border: 2px solid var(--primary-colour);
    margin: 5px;
    border-radius: 5px;
    display: flex;
    flex-direction: column;
    flex-grow: 1;
    align-items: center;
    justify-content: center;
    article {
      padding: 1rem;
    }
  }
  .grid-left {
    display: flex;
    flex-direction: row;
    flex-grow: 1;
  }
  .grid-right {
    width: 50%;
    height: 100%;
    flex-grow: 1;
  }
}

@media only screen and (orientation: portrait) {
  .grid-container {
    flex-wrap: wrap;
  }
}
</style>
