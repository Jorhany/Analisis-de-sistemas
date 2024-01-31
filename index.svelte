<script>
  let name = "Jorhany";
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
    <img src="https://www.bing.com/images/search?view=detailV2&ccid=RP6q%2fIch&id=AAB9F6A75A16C3066AD7A3667E4F2FB3265BF070&thid=OIP.RP6q_IchUHbl6131Mo04pQHaHa&mediaurl=https%3a%2f%2fwww.asofiduciarias.org.co%2fwp-content%2fuploads%2f2018%2f06%2fsin-foto.png&cdnurl=https%3a%2f%2fth.bing.com%2fth%2fid%2fR.44feaafc87215076e5eb5df5328d38a5%3frik%3dcPBbJrMvT35mow%26pid%3dImgRaw%26r%3d0&exph=510&expw=510&q=imagen+de+perfil+sin+foto&simid=608000922578929465&FORM=IRPRST&ck=EDD95CED6C9FCB7FF56CD478FAF33E37&selectedIndex=2&itb=0" alt="Logo de Perfil" />
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
