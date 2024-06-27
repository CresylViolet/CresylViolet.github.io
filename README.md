<center><img style='border:3px solid #000000' src="docs/Untitled design.png" width="1000px" height="200px"></center>



<div style="margin-left:230px;margin-right:230px;text-align:justify">
<h4> 
We are excited to invite you to post your professional development opportunities on the Genomics Education Partnership Professional Development Network (GEPDeN) platform. This initiative aims to connect students and faculty with innovative genomics opportunities. Join us in fostering a vibrant community dedicated to scientific excellence and educational growth. Share your research and/or teaching positions today and help shape the future of genomics education! Get started by filling out the submission form.
</h4>
</div>

<center><img src="docs/helix" width="1000px" height="100px"></center>

<table style="width:50%" align="center" id="Table">
  <tr>
    <th>Posting Title</th>
    <th>Category</th>
    <th>Date Posted</th>
    <th>Closing Date</th>
  </tr>
  <tr>
    <td style="text-align: center"><a href="https://cresylviolet.github.io/pages/alleninstitute.html">Teaching Faculty Needed</a></td>
    <td style="text-align: center">Faculty Positions</td>
    <td style="text-align: center">June 27, 2024</td>
    <td style="text-align: center">August 1, 2024</td>
  </tr>
</table>

<input type="text" id="myInput" onkeyup="filterTable()" placeholder="Search for names..">

<!-- Table to be filtered -->
<table id="myTable">
  <thead>
    <tr>
      <th>Name</th>
      <th>Age</th>
      <th>City</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John Doe</td>
      <td>30</td>
      <td>New York</td>
    </tr>
    <tr>
      <td>Jane Smith</td>
      <td>25</td>
      <td>Los Angeles</td>
    </tr>
    <tr>
      <td>Mike Johnson</td>
      <td>40</td>
      <td>Chicago</td>
    </tr>
    <tr>
      <td>Sarah Brown</td>
      <td>35</td>
      <td>Houston</td>
    </tr>
  </tbody>
</table>

<script>
function filterTable() {
  // Declare variables
  var input, filter, table, tr, td, i, txtValue;
  input = document.getElementById("myInput");
  filter = input.value.toUpperCase();
  table = document.getElementById("myTable");
  tr = table.getElementsByTagName("tr");

  // Loop through all table rows, and hide those who don't match the search query
  for (i = 0; i < tr.length; i++) {
    td = tr[i].getElementsByTagName("td")[0]; // Change index to match the column you want to filter (0-based index)
    if (td) {
      txtValue = td.textContent || td.innerText;
      if (txtValue.toUpperCase().indexOf(filter) > -1) {
        tr[i].style.display = "";
      } else {
        tr[i].style.display = "none";
      }
    }       
  }
}
</script>
