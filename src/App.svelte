<script lang="ts">
  let about = false;
  let release = false;

  function handleAbout() {
    if (release) release = false;
    about = !about;
  }

  function handleRelease() {
    if (about) about = false;
    release = !release;
  }

  $: aboutText = about ? "Voltar" : "Saiba mais";

  $: releaseText = release ? "Voltar" : "Lançamento";
</script>

<main>
  <div class="flex justify-between items-center bg-blue-200 min-h-screen">
    <div />
    {#if !about && !release}
      <div class="flex flex-col justify-center items-center">
        <h1 class="text-9xl text-pink-400">PostBoard</h1>
        <h2 class="text-3xl text-gray-500">Em breve...</h2>
      </div>
    {:else if release}
      <div class="flex flex-col justify-center items-center space-y-2">
        <h1 class="text-3xl font-semibold text-gray-600">
          Cronograma de atividades:
        </h1>
        <h2 class="text-lg text-gray-600">
          Fique atento! Falta pouco para facilitarmos a sua vida.
        </h2>
        <div class="flex space-x-4 h-28 items-end">
          <div class="flex flex-col space-y-2">
            <div class="flex justify-center w-44 text-gray-600">
              Estamos aqui...
            </div>
            <div
              class="flex justify-center bg-pink-300 text-gray-700 w-44 py-2 rounded-lg"
            >
              Concepção
            </div>
          </div>
          <div
            class="flex justify-center bg-gray-300 text-gray-500 w-44 py-2 rounded-lg"
          >
            Desenvolvimento
          </div>
          <div
            class="flex justify-center bg-gray-300 text-gray-500 w-44  py-2 rounded-lg"
          >
            Lançamento
          </div>
          <div
            class="flex justify-center bg-gray-300 text-gray-500 w-44  py-2 rounded-lg"
          >
            Marketing
          </div>
        </div>
      </div>
    {:else}
      <div class="bg-pink-300 p-4 rounded-lg">
        <div
          class="flex flex-col justify-start items-start text-gray-700 space-y-8 w-96"
        >
          <p class="text-2xl font-semibold">Olá, estudante universitário!</p>
          <div class="flex flex-col text-xl space-y-4">
            <p>
              Muito prazer, sou o PostBoard! De agora em diante, vou te ajudar a
              entregar seus trabalhos acadêmicos de forma muito mais prática,
              rápida e transparente!
            </p>
            <p>
              O PostBoard vai ser a solução que você esperava para postagem e
              entrega de atividades, sejam elas acadêmicas, políticas e sociais!
            </p>
            <p>
              Apenas cadastre uma atividade, mande o link para os interessados,
              e pronto!
            </p>
          </div>
        </div>
      </div>
    {/if}
    <div class="flex flex-col px-2 space-y-4">
      <button
        on:click={handleAbout}
        class="bg-pink-300 text-gray-800 w-28 py-2  rounded-lg"
      >
        {aboutText}
      </button>
      <button
        on:click={handleRelease}
        class="bg-pink-300 text-gray-800 w-28 py-2  rounded-lg"
      >
        {releaseText}
      </button>
    </div>
  </div>
</main>
