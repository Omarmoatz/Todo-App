<template>
  <div class="container">
      <h1 class="text-center mt-5">ToDo App</h1>
      <div class="d-flex mt-5">
        <input class="form-control w-100 " type="text" name="text">
        <button class="btn btn-warning" type="button">Add</button>
      </div>
  </div>
  <div class="container">
    <table class="table table-striped table-hover mt-5 table-bordered ">
      <thead>
        <tr>
          <th scope="col">Task</th>
          <th scope="col">Status</th>
          <th scope="col">Edit</th>
          <th scope="col">Delete</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th scope="row"> study js </th>
          <td>todo</td>
          <td>
            <div>
              <span class="fa fa-pen" ></span>
            </div>
          </td>
          <td>
            <div>
              <span class="fa fa-trash" ></span>
            </div>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default{
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

