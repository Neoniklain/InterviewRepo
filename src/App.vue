<script>
/*
 ** Задания ниже лучше выполнять поочередно
 * 2 Исправить ошибки в template
 * 3 Починить добавление книг
 * 4 Добавить удаление книг
 * 5 Сделать так, чтобы при добавлении одинаковых книг появлялся счетчик
 * 6 Сделать так, чтобы всплывающее сообщение было корректным (удаление\добавление)
 * 7 Починить то, что сообщение о состоянии корзины исчезает
 * 8 Сделать так, чтобы сообщение "Коризна пуста" появлялась при первом входе
 * 9 Добавить асинхронный метод, который будет ждать 10 секунд
     и показывать сообщение с просьбой добавить книгу
 * 10 Отменять метод из пункта 9 если книга была добавлена раньше чем появилось сообщение
 * 11 Получить данные книг из https://6294d445a7203b3ed0721dc3.mockapi.io/books с использованием fetch
 */

import Popup from "/src/components/Popup";

export default {
  name: "App",
  components: {
    Popup,
  },
  data() {
    return {
      books: [
        { id: 1, name: "Book 1" },
        { id: 2, name: "Book 2" },
        { id: 3, name: "Book 3" },
        { id: 4, name: "Book 4" },
        { id: 5, name: "Book 5" },
      ],
      cart: [],
      text: "",
    };
  },
  watch: {},
  async mounted() {},
  methods: {
    add(book) {
      this.text = `Книга ${book.name} добавлена.`;
      this.books1.push(book);
    },
  },
};
</script>

<template>
  <div id="app">
    <div class="book-list">
      <div v-for="book in books" class="book-list__item" @click="add">
        {{ book.name }} (нажмите чтобы добавить)
      </div>
    </div>

    <div>Корзина</div>
    <div class="book-list">
      <div class="book-list__item">Первая книга:</div>
      <div v-for="book in cart" @click="" class="book-list__item">
        {{ book.name }} (нажмите чтобы удалить)
      </div>
    </div>

    <Popup :text="text" />
  </div>
</template>

<style lang="scss">
.app {
  height: 100vh;
}

.book-list {
  display: flex;
  flex-direction: column;

  &__item {
    display: inline-block;
    padding: 8px;
    border: 1px solid black;
    margin-bottom: 4px;
  }
}
</style>
