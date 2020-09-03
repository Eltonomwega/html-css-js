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


