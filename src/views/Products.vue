<template>
  <nav>
    <router-link class="but" to="/Login">EXIT CANDY WORLD</router-link>
  </nav>
  <div class="container d-flex justify-content-end mb-3 mt-5 pt-4">
    <div class="d-flex w-25 ms-3">
      <label for="" class="form-label">Sort by category</label>

      <select
        class="form-select"
        name=""
        id="sortCategory"
        onchange="sortCategory()"
      >
        <option value="All">All</option>
        <option value="Snacks">Snacks</option>
        <option value="Sweets">Sweets</option>
        <option value="Drinks">Drinks</option>
      </select>
    </div>

    <div class="d-flex w-25 ms-3">
      <label for="" class="form-label">Sort by name</label>
      <select class="form-select" name="" id="sortName" onchange="sortName()">
        <option value="ascending">Ascending</option>
        <option value="descending">Descending</option>
      </select>
    </div>
    <div class="d-flex w-25 ms-3">
      <label for="" class="form-label">Sort by price</label>
      <select class="form-select" name="" id="sortPrice" onchange="sortPrice()">
        <option value="ascending">Ascending</option>
        <option value="descending">Descending</option>
      </select>
    </div>
    <button
      type="button"
      class="btn btn-primary"
      data-bs-toggle="modal"
      data-bs-target="#exampleModal"
    >
      Add a product
    </button>
    <button type="button" class="btn btn-primary">Cart</button>
  </div>
  <br />
  <hr />
  <!-- Button trigger modal -->

  <!-- Modal -->
  <div
    class="modal fade"
    id="exampleModal"
    tabindex="-1"
    aria-labelledby="exampleModalLabel"
    aria-hidden="true"
  >
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="exampleModalLabel">Add product</h5>
          <button
            type="button"
            class="btn-close"
            data-bs-dismiss="modal"
            aria-label="Close"
          ></button>
        </div>
        <div class="modal-body">
          <div class="modal-content">
            <div class="modal-body">
              <div class="mb-3">
                <label for="addTitle" class="form-label">Title</label>
                <input
                  class="form-control"
                  type="text"
                  name="addTitle"
                  id="addTitle"
                />
              </div>
              <div class="mb-3">
                <label for="" class="form-label">Category</label>
                <select class="form-select" name="addCategory" id="addCategory">
                  <option value="Snacks">Snacks</option>
                  <option value="Sweets">Sweets</option>
                  <option value="Drink">Drink</option>
                </select>
              </div>
              <div class="mb-3">
                <label for="addPrice" class="form-label">Price</label>
                <input
                  class="form-control"
                  type="text"
                  name="addPrice"
                  id="addPrice"
                />
              </div>
              <div class="mb-3">
                <label for="addImg" class="form-label">Image URL</label>
                <input
                  class="form-control"
                  type="text"
                  name="addImg"
                  id="addImg"
                />
              </div>
            </div>
            <div class="modal-footer">
              <button
                type="button"
                class="btn btn-secondary"
                data-bs-dismiss="modal"
              >
                Close
              </button>
              <button
                type="button"
                class="btn btn-primary"
                data-bs-dismiss="modal"
                onclick="createProduct()"
              >
                Create Product
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <div class="container my-5">
    <div v-if="products.length" class="row">
      <div
        v-for="product of products"
        :key="product._id"
        class="col-lg-4 col-md-6 col-sm-12"
      >
        <div
          class="card testimonial-card shadow-5-strong mt-2 mb-3 pt-4 animate__animated animate__jackInTheBox"
        >
          <div class="card-up aqua-gradient"></div>
          <div class="avatar mx-auto white">
            <img
              :src="product.img"
              class="rounded-circle img-fluid test-img"
              alt="Kagiso"
            />
          </div>
          <div class="card-body text-center">
            <h4 class="card-title font-weight-bold">
              {{ product.title }}
            </h4>
            <hr />
            <p>
              <i class="fas fa-quote-left"></i> {{ product.category }}
              <i class="fas fa-quote-right"></i>
            </p>
            <p class="card-text">
              <small class="text-muted">R{{ product.price }}</small>
            </p>
          </div>
        </div>
      </div>
    </div>
    <div v-else>
      <p>Loading products...</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [],
    };
  },
  mounted() {
    if (localStorage.getItem("jwt")) {
      fetch("https://pos-bkend.herokuapp.com/products/", {
        method: "GET",
        headers: {
          "Content-type": "application/json; charset=UTF-8",
          Authorization: `Bearer ${localStorage.getItem("jwt")}`,
        },
      })
        .then((response) => response.json())
        .then((json) => {
          this.products = json;
          this.products.forEach(async (product) => {
            await fetch(
              "https://pos-bkend.herokuapp.com/products/ " + product.created_by,
              {
                method: "GET",
                headers: {
                  "Content-type": "application/json; charset=UTF-8",
                  Authorization: `Bearer ${localStorage.getItem("jwt")}`,
                },
              }
            )
              .then((response) => response.json())
              .then((json) => {
                product.created_by = json.title;
              });
          });
        })
        .catch((err) => {
          alert("User not logged in");
        });
    } else {
      alert("User not logged in");
      this.$router.push({ name: "Login" });
    }
  },
};
</script>

<style>
.btn {
  background-color: #5ce1e6 !important;
}
</style>
