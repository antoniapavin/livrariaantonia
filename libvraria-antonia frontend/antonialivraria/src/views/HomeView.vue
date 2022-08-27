<script>
export default {
  data() {
    return {
      livros: [
        {
          id: 1,
          nome: "Quando Ninguém está Olhando",
          descricao:
            "Sydney Green nasceu e foi criada no Brooklyn, em Nova York, mas cada vez que ela pisca os olhos seu amado bairro parece mudar. Condomínios se espalham como erva daninha, placas de “vende-se” surgem da noite para o dia e os vizinhos que ela conhece a vida toda estão sumindo.",
          imagem: new URL(
            "https://images-na.ssl-images-amazon.com/images/I/61mSM2HNf6L.jpg",
            import.meta.url
          ).href,
        },
      ],
    };
  },
  methods: {
    comprarLivro(livro) {
      alert("Você adicionou " + livro.nome + " na sacola");
    },
  },
};
</script>
<template>
  <div class="margin">
    <div class="row row-cols-1 row-cols-md-5 g-4">
      <div class="col" v-for="livro of livros" :key="livro.id">
        <div class="card">
          <img
            id="oi"
            :src="livro.imagem"
            class="card-img-top img-cards"
            alt="..."
          />
          <div class="card-body">
            <h5 class="card-title">{{ livro.nome }}</h5>
            <p class="card-text">
              {{ livro.descricao }}
            </p>
            <button
              type="button"
              class="btn btn-secondary botao-meu"
              @click="comprarLivro(livro)"
            >
              Comprar
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

