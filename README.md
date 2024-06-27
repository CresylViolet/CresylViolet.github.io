<center><img style='border:3px solid #000000' src="docs/Untitled design.png" width="1000px" height="200px"></center>



<div style="margin-left:230px;margin-right:230px;text-align:justify">
<h4> 
We are excited to invite you to post your professional development opportunities on the Genomics Education Partnership Professional Development Network (GEPDeN) platform. This initiative aims to connect students and faculty with innovative genomics opportunities. Join us in fostering a vibrant community dedicated to scientific excellence and educational growth. Share your research and/or teaching positions today and help shape the future of genomics education! Get started by filling out the submission form.
</h4>
</div>

<center><img src="docs/helix" width="1000px" height="100px"></center>

<center><input type="text" id="filterName" onkeyup="filterTable()" placeholder="Search by posting title"></center>
<center><input type="text" id="filterAge" onkeyup="filterTable()" placeholder="Search by category"></center>

<!-- Table to be filtered -->
<table id="myTable" style="width:50%" align="center">
  <thead>
    <tr>
    <th onclick="sortTable(0)">Posting Title</th>
    <th onclick="sortTable(1)">Category</th>
    <th onclick="sortTable(2)">Date Posted</th>
    <th onclick="sortTable(3)">Closing Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
    <td style="text-align: center"><a href="https://cresylviolet.github.io/pages/alleninstitute.html">Teaching Faculty Needed</a></td>
    <td style="text-align: center">Faculty Positions</td>
    <td style="text-align: center">June 27, 2024</td>
    <td style="text-align: center">August 1, 2024</td>
    </tr>
    <tr>
    <td style="text-align: center"><a href="https://cresylviolet.github.io/pages/alleninstitute.html">Teaching Faculty Needed</a></td>
    <td style="text-align: center">Postdoctorral</td>
    <td style="text-align: center">June 27, 2024</td>
    <td style="text-align: center">August 1, 2024</td>
    </tr>
  </tbody>
</table>

<script>
function filterTable() {
  // Declare variables
  var inputName, inputAge, inputCity, filterName, filterAge, filterCity, table, tr, tdName, tdAge, tdCity, i;
  inputName = document.getElementById("filterName");
  inputAge = document.getElementById("filterAge");
  filterName = inputName.value.toUpperCase();
  filterAge = inputAge.value.toUpperCase();
  table = document.getElementById("myTable");
  tr = table.getElementsByTagName("tr");

  // Loop through all table rows, and hide those who don't match the search query
  for (i = 0; i < tr.length; i++) {
    tdName = tr[i].getElementsByTagName("td")[0];
    tdAge = tr[i].getElementsByTagName("td")[1];
    if (tdName || tdAge || tdCity) {
      var nameMatch = tdName.textContent.toUpperCase().indexOf(filterName) > -1;
      var ageMatch = tdAge.textContent.toUpperCase().indexOf(filterAge) > -1;
      if (nameMatch && ageMatch && cityMatch) {
        tr[i].style.display = "";
      } else {
        tr[i].style.display = "none";
      }
    }       
  }
}
