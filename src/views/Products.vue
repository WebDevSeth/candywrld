<template>
 <header class="p-3 text-white">
    <div class="container">
      <div class="d-flex flex-wrap align-items-center justify-content-center justify-content-lg-start">
        <a href="/" class="d-flex align-items-center mb-2 mb-lg-0 text-white text-decoration-none">
          <svg class="bi me-2" width="40" height="32" role="img" aria-label="Bootstrap"><use xlink:href="#bootstrap"/></svg>
        </a>



        <div class="text-end">
          <router-link class="btn" to="/Login">Sign out</router-link>
          <button type="button" class="btn"  data-bs-toggle="modal" data-bs-target="#exampleModal2">Update Profile</button>
          <button type="button" class="btn" data-bs-toggle="modal" data-bs-target="#exampleModal">
         Add a product
      </button>
       <button type="button" class="btn" >
         Cart
      </button>
      
        </div>
             <div class="d-flex w-25 ms-3">
         

         <select class="form-select" name="" id="sortCategory" onchange="sortCategory()">

            <option value="category">Sort by category </option>
            <option value="All">All</option>
            <option value="Snacks">Snacks</option>
            <option value="Sweets">Sweets</option>
            <option value="Drinks">Drinks</option>
         </select>
         
           <div class="d-flex w-25 ms-3">
         
         <select class="form-select" name="" id="sortName" onchange="sortName()">
             <option value="name">Sort by name</option>
            <option value="ascending">Ascending</option>
            <option value="descending">Descending</option>
         </select>
            <div class="d-flex w-25 ms-3">
      
         <select class="form-select" name="" id="sortPrice" onchange="sortPrice()">
             <option value="price">Sort by price</option>
            <option value="ascending">Ascending</option>
            <option value="descending">Descending</option>
         </select>
      </div>
      </div>
      </div>

   

      </div>
    </div>
  </header>

<div class="container d-flex w-25 ms-3">
   

</div>

   <div class="container d-flex justify-content-end mb-3 mt-5 pt-4">
      
 

 
      
      
   </div>
   <br />
   <hr />
   <!-- Button trigger modal -->


   <!-- Modal -->
   <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
      <div class="modal-dialog">
         <div class="modal-content">
      
            <div class="modal-body">
               <div class="modal-content">
                  <div class="modal-body">
                     <div class="mb-3">
                        <label for="addTitle" class="form-label">Product title</label>
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

   <!-- modal 2 -->

   <div class="modal fade" id="exampleModal2" tabindex="-1" aria-labelledby="exampleModalLabel2" aria-hidden="true">
      <div class="modal-dialog">
         <div class="modal-content">
      
            <div class="modal-body">
               <div class="modal-content">
                  <div class="modal-body">
                     <div class="mb-3">
                        <label for="addTitle" class="form-label">Email</label>
                        <input class="form-control" type="text" name="addTitle" id="addTitle" />
                     </div>
                  
                     <div class="mb-3">
                        <label for="addPrice" class="form-label">Password</label>
                        <input class="form-control" type="text" name="addPrice" id="addPrice" />
                     </div>
                     <div class="mb-3">
                        <label for="addImg" class="form-label">Confirm Password</label>
                        <input class="form-control" type="text" name="addImg" id="addImg" />
                     </div>
                     
                  </div>
                  <div class="modal-footer">
                     <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">
                        Close
                     </button>
                     <button type="button" class="btn btn-primary" data-bs-dismiss="modal" onclick="createProduct()">
                        Update user
                     </button>
                  </div>

               </div>
            </div>
         </div>
      </div>

   </div>

</template>

<script>

</script>

<style>
   .btn {
      background-color: #5ce1e6 !important;

   }


   .form-select {
      width: 180px !important;
      height: 70px  !important;
      background-color: white !important;
   }

   .form-control {
      background-color: white !important;
   }

   
</style>