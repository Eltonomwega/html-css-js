<!-- THIS IS A COMMENT/ALSO MULTILINE -->

<!-- 

    FUNDAMENTALS: https://www.internetingishard.com/

 -->
<!-- 

    CHALLENGE

    A basic(responsive) html page with a form to post to a backend and display a list of responses?

 -->

<!-- 
     BIOLERPLATE 
    https://www.sitepoint.com/a-basic-html5-template/

    -->
<!doctype html>

<html lang="en">

<head>
  <meta charset="utf-8">

  <title>HTML5 BOILERPLATE</title>
  <meta name="description" content="HTML5 BOILERPLATE">
  <meta name="author" content="SitePoint">
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css"
   integrity="sha384-JcKb8q3iqJ61gNV9KGb8thSsNjpSL0n8PARn9HuZOnIxN0hoP+VmmDGMN5t9UJ0Z" 
   crossorigin="anonymous">

  <link rel="stylesheet" href="styles.fundamentals.css">

</head>

<body>

  <div class="container">
    <div class="header">

    </div>
    <div class="content">

      <div class="form-container">
        <form class="">
          <div class="row">
            <div class="col-25">
              <label for="fname">Your Input Here</label>
            </div>
            <div class="col-75">
              <input type="text" id="userInput" placeholder="Your input here..">
            </div>
          </div>
          <div class="row">
            <input type="submit" value="Submit">
          </div>
        </form>
      </div>

      <table class="table">
        <thead>
          <tr>
            <th scope="col">#</th>
            <th scope="col">response</th>
          </tr>
        </thead>
        <tbody id="tbody">
          
  
        </tbody>
      </table>

    </div>


  </div>

  <div class="footer">

  </div>
  </div>

  <script>
        //counting the responses
         var counter = 0;

         //function to create the table
          function createTable(data){
          var tbody = document.getElementById("tbody");
          var tr = document.createElement("tr");
          var th = document.createElement("th");
          var td = document.createElement("td");

          for(var i=0; i< data.length;i++){
            tbody.appendChild(tr);

            tr.appendChild(th);
            th.appendChild(document.createTextNode(++counter));
            tr.appendChild(td);
            td.appendChild(document.createTextNode(data[i]))
          }
          //clearing the array to avoid duplicate responses
          data.length = 0;
        }

          var words = [];

          let element = document.getElementById("userInput");
          addEventListener("submit", function(event) {
          event.preventDefault();

          console.log(element.value);

          //check if response is empty
          if(element.value == ""){
            alert("response can not be empty");
          }else{
          words.push(element.value);
          createTable(words);

          }
          });
          

/*
PLACE CHALLENGE CODE HERE THAT DEALS WITH DON MANIPULATION
*/
  </script>
    <!-- JS, Popper.js, and jQuery -->
<script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"
integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj"
 crossorigin="anonymous"></script>
<script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.1/dist/umd/popper.min.js"
integrity="sha384-9/reFTGAW83EW2RDu2S0VKaIzap3H66lZH81PoYlFhbGU+6BZp6G7niu735Sk7lN"
 crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js" 
integrity="sha384-B4gt1jrGC7Jh4AgTPSdUtOBvfO8shuf57BaghqFfPlYxofvL8/KUEfYiJOMMV+rV" 
crossorigin="anonymous"></script>
</body>

</html>