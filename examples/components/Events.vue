<template>
  <div class="row">
    <div class="blocks">
      <h3 class="text-center mt-5">Events</h3>
      <div class="block">
        <table class="table table-responsive d-table">
          <thead>
            <tr>
              <th>event</th>
              <th>Comment</th>
              <th>Params</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>change</td>
              <td>Trigger when the value of province, city, area has changed.</td>
              <td>Return array (province, city, area)</td>
            </tr>
            <tr>
              <td>confirm</td>
              <td>Trigger when confirm your selected.</td>
              <td>Return array (province, city, area)</td>
            </tr>
            <tr>
              <td>cancel</td>
              <td>Trigger when cancel to select.</td>
              <td>Null</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>
