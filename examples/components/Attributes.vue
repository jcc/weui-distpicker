<template>
  <div class="row">
    <div class="blocks">
      <h3 class="text-center mt-5">Attributes</h3>
      <div class="block">
        <table class="table table-responsive d-table">
          <thead>
            <tr>
              <th>Param</th>
              <th>Comment</th>
              <th>Type</th>
              <th>Optional</th>
              <th>Default</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>province</td>
              <td>Determine whether to set the default for province.</td>
              <td>String | Number</td>
              <td>customize</td>
              <td>null</td>
            </tr>
            <tr>
              <td>city</td>
              <td>Determine whether to set the default for city.</td>
              <td>String | Number</td>
              <td>customize</td>
              <td>null</td>
            </tr>
            <tr>
              <td>area</td>
              <td>Determine whether to set the default for area.</td>
              <td>String | Number</td>
              <td>customize</td>
              <td>null</td>
            </tr>
            <tr>
              <td>className</td>
              <td>Textarea line-height style.</td>
              <td>String</td>
              <td>customize</td>
              <td>null</td>
            </tr>
            <tr>
              <td>onlyProvince</td>
              <td>Textarea placeholder.</td>
              <td>Boolean</td>
              <td>true, false</td>
              <td>false</td>
            </tr>
            <tr>
              <td>hideArea</td>
              <td>Textarea rows.</td>
              <td>Boolean</td>
              <td>true, false</td>
              <td>false</td>
            </tr>
            <tr>
              <td>cache</td>
              <td>Textarea rows.</td>
              <td>Boolean</td>
              <td>true, false</td>
              <td>true</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>
