<template>
    <div id="app">
  <ul>
    <li v-for="item in paginatedItems" :key="item.id">{{ item.name }}</li>
  </ul>

  <ul class="pagination">
    <li class="pagination-button" @click="prevPage" :disabled="currentPage === 1">&lt; Prev</li>
    <li class="pagination-item" v-for="pageNumber in totalPages" :key="pageNumber" @click="changePage(pageNumber)" :class="{ active: currentPage === pageNumber }">
      {{ pageNumber }}
    </li>
    <li class="pagination-button" @click="nextPage" :disabled="currentPage === totalPages">Next &gt;</li>
  </ul>
</div>    
</template>
<script>
export default {
    data(){
        return{
            items: [
        { id: 1, name: 'Item 1' },
        { id: 2, name: 'Item 2' },
        { id: 3, name: 'Item 3' },
        { id: 4, name: 'Item 4' },
        { id: 5, name: 'Item 5' },
        { id: 6, name: 'Item 6' },
        { id: 7, name: 'Item 7' },
        { id: 8, name: 'Item 8' }
       
      ],
      itemsPerPage: 2,
      currentPage: 1
        }
    },
    computed: {
      totalPages() {
        return Math.ceil(this.items.length / this.itemsPerPage);
      },
      paginatedItems() {
        const start = (this.currentPage - 1) * this.itemsPerPage;
        const end = start + this.itemsPerPage;
        console.log(this.items.slice(start, end));
        return this.items.slice(start, end);
      }
    },
    methods: {
      changePage(pageNumber) {
        this.currentPage = pageNumber;
      },
      prevPage() {
        if (this.currentPage > 1) {
          this.currentPage--;
        }
      },
      nextPage() {
        if (this.currentPage < this.totalPages) {
          this.currentPage++;
        }
      },
    }
}
</script>
<style scoped>
#app {
      font-family: Arial, sans-serif;
      margin: 20px;
    }

    .pagination {
      display: flex;
      list-style: none;
      padding: 0;
    }

    .pagination-item,
    .pagination-button {
      margin: 0 5px;
      cursor: pointer;
    }

    .pagination-item.active {
      font-weight: bold;
    }
</style>