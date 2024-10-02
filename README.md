<!DOCTYPE html>

<html lang="en"> grid

<head>

<link rel="stylesheet" href="style2.css"> <link

"stylesheet"> href="https://fonts.googleapis.com/css?family=Montserrat:wght@300;400;500;600; 700&display=swap" rel="st

<meta charset="UTF-8 ">

meta name="viewport" content="width=device-width, initial-scale=1.0"> <

<title>Book Search Page</title>

<script src="https://code.jquery.com/jquery-2.1.4.min.js"></script>

</head>

<body> grid

<nav></nav> <div class="content">

<h1 id="title">Book Search</h1>

<h2>

<span id="searchTermDisplay"></span>

"Searched "

<!-- search button -->

<label for="searchTerm">Search for books:</label>

</h2>

<input type="text" id="searchTerm" placeholder="Enter book title">

<div>

<button id="searchButton">Search</button>

<!-- Paging control for navigating between results s -->

<div>

</div>

<label for="pageSelect">Select Page:</label> ▼<select id="pageSelect">

<option value="0">Page 1</option> slot

<option value="15">Page 2</option> slot

<option value="30">Page 3</option> slot

<option value="45">Page 4</option> slot

</select>

</div>

<div id="results" style="display: flex; flex-wrap: wrap"></div>  
<script>

$(function () {

function fetchResults (startIndex) {

if (!term) {

return;

}

var resultsPerPage = 15; term + "&startIndex=" startIndex + "&maxResults=" + resultsPerPage;

var term = $("#searchTerm").val(); // get value from input box

var parameter = "?q=" +

alert("Please enter a search rm");

return;

}

var resultsPerPage = 15;

var parameter =

"?q=" +

term +

"&startIndex=" +

startIndex +

"&maxResults=" +

return;

"https://www.googleapis.com/books/v1/volumes/" + parameter;

resultsPerPage; var service_point =

$.getJSON(service_point, function (json) {

var total = json.totalItems;

$("#total").text(total);

var resultHTML = "";

var booktitle = json.items[i].volumeInfo.title;

for (i in json.items) {

var bookid= json.items[i].id;

var cover = "";

if (json.items[i].volumeInfo.imageLinks != null)

cover = json.items[i].volumeInfo.imageLinks.thumbnail;

resultHTML += "<div class='bookdiv'>"; resultHTML += "<img src='" + cover + style='float: left" />";

resultHTML +=

"<a href='book_details.html?id=" + bookid +

Mer Memory

Application +

"'>" + booktitle +

"</a>"; resultHTML += "</div>";

}

$("#results").html(resultHTML);

$(".bookdiv").css("width", "300px");

});

Searched

Search for boo

Select Page: F

}

// Trigger search when button is clicked $("#searchButton").click(function () {

var term = $("#searchTerm").val();

$("#searchTermDisplay").text(term); // Update the search term display

fetchResults(0); // Fetch results for page 1 (startIndex)

// Change event to fetch the appropriate page based on the user's selection

});

$("#pageSelect").change(function () { this).val() ;

});

var startIndex = $( fetchResults(startIndex);
}); = $0
</script>



</div>

<div>
<footer></footer>
</div>
</body>
</html>
