<template>
  <nav>
    <router-link class="but" to="/Login">SIGN OUT</router-link>
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
    <button
      type="button"
      class="btn btn-primary"
      data-bs-toggle="modal"
      data-bs-target="#exampleModal2"
    >
      Update user <i class="bi bi-person-circle"></i>
    </button>
   <router-link class="btn btn-primary" to="/Cart">Cart</router-link> 
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
        <button
          type="button"
          class="btn-close"
          data-bs-dismiss="modal"
          aria-label="Close"
        ></button>

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
              <div class="mb-3">
                <label for="addImg" class="form-label">Description</label>
                <input
                  class="form-control"
                  type="text"
                  name="addImg"
                  id="addImg"
                />
              </div>
            </div>

            <button
              type="button"
              class="btn btn-secondary"
              data-bs-dismiss="modal"
            >
              Close
            </button>
            <br />
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

  <!-- modal2 -->

  <div
    class="modal fade"
    id="exampleModal2"
    tabindex="-1"
    aria-labelledby="exampleModalLabel"
    aria-hidden="true"
  >
    <div class="modal-dialog">
      <div class="modal-content">
        <button
          type="button"
          class="btn-close"
          data-bs-dismiss="modal"
          aria-label="Close"
        ></button>

        <div class="modal-body">
          <div class="modal-content">
            <div class="modal-body">
              <div class="mb-3">
                <label for="addTitle" class="form-label">Name</label>
                <input
                  class="form-control"
                  type="text"
                  name="addTitle"
                  id="addTitle"
                />
              </div>
              <div class="mb-3">
                <label for="addPrice" class="form-label">Email</label>
                <input
                  class="form-control"
                  type="text"
                  name="addPrice"
                  id="addPrice"
                />
              </div>
              <div class="mb-3">
                <label for="addImg" class="form-label">Password</label>
                <input
                  class="form-control"
                  type="text"
                  name="addImg"
                  id="addImg"
                />
              </div>
            </div>

            <button
              type="button"
              class="btn btn-secondary"
              data-bs-dismiss="modal"
            >
              Close
            </button>
            <br />
            <button
              type="button"
              class="btn btn-primary"
              data-bs-dismiss="modal"
              onclick="createProduct()"
            >
              Update User
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>



  <!-- modal3 -->

  <div
    class="modal fade"
    id="exampleModal3"
    tabindex="-1"
    aria-labelledby="exampleModalLabel"
    aria-hidden="true"
  >
    <div class="modal-dialog">
      <div class="modal-content">
        <button
          type="button"
          class="btn-close"
          data-bs-dismiss="modal"
          aria-label="Close"
        ></button>

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
              <div class="mb-3">
                <label for="addImg" class="form-label">Description</label>
                <input
                  class="form-control"
                  type="text"
                  name="addImg"
                  id="addImg"
                />
              </div>
            </div>

            <button
              type="button"
              class="btn btn-secondary"
              data-bs-dismiss="modal"
            >
              Close
            </button>
            <br />
            <button
              type="button"
              class="btn btn-primary"
              data-bs-dismiss="modal"
              onclick="createProduct()"
            >
              Edit Product
            </button>
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
        <div class="card">
          <img :src="product.img" class="card-img-top" :alt="product.title" />
          <div class="card-body">
            <h5 class="card-title">{{ product.title }}</h5>
            <p class="card-text">R{{ product.price }}</p>
            <p class="card-text">{{ product.category }}</p>
            <p class="card-text">{{ product.description }}</p>
            <div class="d-flex mb-3">
              <input
                type="number"
                class="form-control"
                value="1"
                min="1"
                id="addToCart${position}"
              />
              <button
                type="button"
                class="btn2"
                onclick="addToCart(${position})"
              >
                <i class="fas fa-cart-plus"></i>
              </button>
            </div>
          </div>
          <div class="d-flex justify-content-end card-footer">
            <button
             type="button"
      class="btn btn-primary"
      data-bs-toggle="modal"
      data-bs-target="#exampleModal3"
            >
              Edit
            </button>
            <button
              type="button"
              class="btn btn-danger w-50 ms-3"
              onclick="deleteProduct(${position})"
            >
              Delete
            </button>
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

.btn2 {
  border-left: 0 !important;
  border-right: 0 !important;
  border-bottom: 0 !important;
  border-top: 0 !important;
  padding: 10px !important;
}

.card-img-top {
  max-height: 400px;
}

.form-select {
  background-color: white !important;
}

.form-control {
  background-color: white !important;
  widows: 100% !important;
}

.card-body {
  background-color: white !important;
}

.card-title {
  background-color: white !important;
}

.card-text {
  background-color: white !important;
}

.bi {
  background-color: #5CE1E6!important;
}

.fas {
  background-color: #5CE1E6!important;
}

.card-footer {
  background-color: white !important;
}

.card {
  margin: 10px !important;
}

.fas {
  background-color: #FF66C4 !important;
}
</style>
