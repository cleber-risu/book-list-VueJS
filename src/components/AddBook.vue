<script setup>
let newBook = {
  title: "",
  cover: "",
  isRead: false,
  isbn: "",
  author: "",
};
</script>

<template>
  <h1>📖 Adicionar Livro</h1>

  <div class="header-btns">
    <button class="btn" @click="$emit('closeAddBook')">Fechar x</button>
  </div>

  <form class="add-form">
    <div class="form-control">
      <label>Título</label>
      <input
        type="text"
        name="text"
        placeholder="Adicione o título"
        required
        v-model="newBook.title"
      />
    </div>
    <div class="form-control">
      <label>Capa</label>
      <input
        type="url"
        name="cover"
        placeholder="Adicione o link da imagem de capa"
        required
        v-model="newBook.cover"
      />
    </div>
    <div class="form-control">
      <label>Autor</label>
      <input
        type="text"
        name="author"
        placeholder="Adicione o autor"
        v-model="newBook.author"
      />
    </div>
    <div class="form-control">
      <label>ISBN#</label>
      <input
        type="text"
        name="isbn"
        placeholder="Adicione o ISBN"
        v-model="newBook.isbn"
      />
    </div>
    <div class="form-control form-control-check">
      <input
        type="checkbox"
        name="readIt"
        id="readIt"
        v-model="newBook.isRead"
      />
      <label for="readIt">Já li o livro</label>
    </div>

    <button
      @click.prevent="$emit('addBook', newBook)"
      type="submit"
      class="btn btn-block"
    >
      Salvar livro
    </button>
  </form>
</template>
