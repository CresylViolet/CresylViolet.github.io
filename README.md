<center><img style='border:3px solid #000000' src="docs/Untitled design.png" width="1000px" height="200px"></center>



<div style="margin-left:230px;margin-right:230px;text-align:justify">
<h4> 
We are excited to invite you to post your professional development opportunities on the Genomics Education Partnership Professional Development Network (GEPDeN) platform. This initiative aims to connect students and faculty with innovative genomics opportunities. Join us in fostering a vibrant community dedicated to scientific excellence and educational growth. Share your research and/or teaching positions today and help shape the future of genomics education! Get started by filling out the submission form.
</h4>
</div>

<center><img src="docs/helix" width="1000px" height="100px"></center>


<!-- Inputs for filtering -->
<center>
<input type="text" id="filterName" style="margin-right:20px" onkeyup="filterTable()" placeholder="Search by Posting Title...">
<input type="text" id="filterAge" style="margin-right:20px" onkeyup="filterTable()" placeholder="Search by Category...">
<input type="text" id="filterCity" onkeyup="filterTable()" placeholder="Search by Date Opened...">
</center>

<!-- Table to be filtered and sorted -->
<table id="myTable" width="1000px" align="center">
  <col width="200">
  <col width="100">
  <col width="100">
  <col width="100">
  <thead>
    <tr>
      <th onclick="sortTable(0)">Posting Title</th>
      <th onclick="sortTable(1)">Category</th>
      <th onclick="sortTable(2)">Date Posted</th>
      <th onclick="sortTable(2)">Date Closing</th>
    </tr>
  </thead>
  <tbody>
    <tr>
    <td style="text-align: center"><a href="https://cresylviolet.github.io/pages/alleninstitute.html">Teaching Faculty Needed</a></td>
    <td style="text-align: center">Faculty Positions</td>
    <td style="text-align: center">June 28, 2024</td>
    <td style="text-align: center">August 4, 2024</td>
    </tr>
    <tr>
    <td><a href="(https://research.ua.edu/our/emerging-scholars-program/)"> University of Alabama Emerging Scholars Program </a></td>
    <td style="text-align: center">Undergraduate Research</td>
    <td style="text-align: center">June 27, 2024</td>
    <td style="text-align: center">Indefinite</td>
    </tr>
  </tbody>
</table>

<script>
// Function to filter the table based on user input
function filterTable() {
  var inputName, inputAge, inputCity, filterName, filterAge, filterCity, table, tr, tdName, tdAge, tdCity, i;
  inputName = document.getElementById("filterName");
  inputAge = document.getElementById("filterAge");
  inputCity = document.getElementById("filterCity");
  filterName = inputName.value.toUpperCase();
  filterAge = inputAge.value.toUpperCase();
  filterCity = inputCity.value.toUpperCase();
  table = document.getElementById("myTable");
  tr = table.getElementsByTagName("tr");

  for (i = 0; i < tr.length; i++) {
    tdName = tr[i].getElementsByTagName("td")[0];
    tdAge = tr[i].getElementsByTagName("td")[1];
    tdCity = tr[i].getElementsByTagName("td")[2];
    if (tdName || tdAge || tdCity) {
      var nameMatch = tdName.textContent.toUpperCase().indexOf(filterName) > -1;
      var ageMatch = tdAge.textContent.toUpperCase().indexOf(filterAge) > -1;
      var cityMatch = tdCity.textContent.toUpperCase().indexOf(filterCity) > -1;
      if (nameMatch && ageMatch && cityMatch) {
        tr[i].style.display = "";
      } else {
        tr[i].style.display = "none";
      }
    }       
  }
}

// Function to sort the table by a specific column
function sortTable(columnIndex) {
  var table, rows, switching, i, x, y, shouldSwitch;
  table = document.getElementById("myTable");
  switching = true;

  // Make a loop that will continue until no switching has been done
  while (switching) {
    switching = false;
    rows = table.rows;

    // Loop through all table rows (except the first, which contains headers)
    for (i = 1; i < (rows.length - 1); i++) {
      shouldSwitch = false;

      // Get the two elements you want to compare, one from current row and one from the next
      x = rows[i].getElementsByTagName("td")[columnIndex];
      y = rows[i + 1].getElementsByTagName("td")[columnIndex];

      // Check if the two rows should switch place
      if (x.innerHTML.toLowerCase() > y.innerHTML.toLowerCase()) {
        shouldSwitch= true;
        break; // Exit the loop if a switch has been marked
      }
    }
    if (shouldSwitch) {
      // If a switch has been marked, make the switch and mark that a switch has been done
      rows[i].parentNode.insertBefore(rows[i + 1], rows[i]);
      switching = true;
    }
  }
}
</script>
