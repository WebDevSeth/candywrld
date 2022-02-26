<template>
   <router-link class="but" to="/Login">SIGN OUT</router-link>

   <div class="container d-flex justify-content-end mb-3 mt-5 pt-4">
      <button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
         Add a product
      </button>
      <div class="d-flex w-25 ms-3">
         <label for="" class="form-label">Sort by category</label>

         <select class="form-select" name="" id="sortCategory" onchange="sortCategory()">

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
   </div>
   <br />
   <hr />
   <!-- Button trigger modal -->


   <!-- Modal -->
   <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
      <div class="modal-dialog">
         <div class="modal-content">
            <div class="modal-header">
               <h5 class="modal-title" id="exampleModalLabel">Add product</h5>
               <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
            </div>
            <div class="modal-body">
               <div class="modal-content">
                  <div class="modal-body">
                     <div class="mb-3">
                        <label for="addTitle" class="form-label">Title</label>
                        <input class="form-control" type="text" name="addTitle" id="addTitle" />
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
                        <input class="form-control" type="text" name="addPrice" id="addPrice" />
                     </div>
                     <div class="mb-3">
                        <label for="addImg" class="form-label">Image URL</label>
                        <input class="form-control" type="text" name="addImg" id="addImg" />
                     </div>
                  </div>
                  <div class="modal-footer">
                     <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">
                        Close
                     </button>
                     <button type="button" class="btn btn-primary" data-bs-dismiss="modal" onclick="createProduct()">
                        Create Product
                     </button>
                  </div>

               </div>
            </div>
         </div>
      </div>

   </div>

</template>

<script>
   export default {
      mounted() {
         // CREATE
         function createProduct() {
            let title = document.querySelector("#addTitle").value;
            let category = document.querySelector("#addCategory").value;
            let price = document.querySelector("#addPrice").value;
            let img = document.querySelector("#addImg").value;

            try {
               if (!title || !price || !img) throw new Error("Please fill in all fields");
               products.push({
                  title,
                  category,
                  price,
                  img,
               });
               localStorage.setItem("products", JSON.stringify(products));
               readProducts(products);
            } catch (err) {
               alert(err);
            }
         }
      }
   }
</script>

<style>
   .btn {
      background-color: #5ce1e6 !important;
   }
</style>