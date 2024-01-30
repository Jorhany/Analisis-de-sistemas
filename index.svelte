<script>
  let name = "John Doe";
  let title = "Web Developer";
  let skills = ["HTML", "CSS", "JavaScript"];

  let comments = [];
  let commentTitle = "";
  let commentText = "";

  function addComment() {
    if (commentTitle && commentText) {
      comments = [...comments, { title: commentTitle, text: commentText }];
      commentTitle = "";
      commentText = "";
    }
  }
</script>

<main>
  <section class="profile-section">
    <img src="ruta/a/tu/logo.png" alt="Logo de Perfil" />
    <div>
      <h2>{name}</h2>
      <p>{title}</p>
      <ul>
        {#each skills as skill}
          <li>{skill}</li>
        {/each}
      </ul>
    </div>
  </section>

  <section class="comments-section">
    <h3>Agregar Comentario</h3>
    <form on:submit|preventDefault={addComment}>
      <label>
        Título:
        <input bind:value={commentTitle} />
      </label>
      <label>
        Comentario:
        <input bind:value={commentText} />
      </label>
      <button type="submit">Agregar</button>
    </form>

    <h3>Comentarios</h3>
    <ul>
      {#each comments as { title, text }}
        <li>
          <strong>{title}:</strong>
          {text}
        </li>
      {/each}
    </ul>
  </section>
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    max-width: 600px;
    margin: 20px auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 8px;
  }

  .profile-section {
    display: flex;
    align-items: center;
    margin-bottom: 20px;
  }

  img {
    width: 100px;
    border-radius: 50%;
    margin-right: 20px;
  }

  h2 {
    margin: 0;
  }

  ul {
    padding: 0;
    list-style-type: none;
  }

  .comments-section {
    margin-top: 20px;
  }

  form {
    margin-bottom: 20px;
  }

  h3 {
    margin-bottom: 10px;
  }

  ul {
    padding: 0;
    list-style-type: none;
  }

  li {
    margin-bottom: 10px;
  }
</style>
