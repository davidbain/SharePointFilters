# SharePointFilters
A-Z filter buttons for SharePoint

These filter buttons allow you to filter a SharePoint list by item name. For example, selecting A shows all items 
starting with 'A'. They work by modifying the simple SharePoint URL to filter the list, meaning a filtered list is
also shareable via it's page URL. 

<div id="DBSPFilterBtns">
    <style>
        #DBSPFilterBtns {
            display: inline-block;
        }
        #DBFilterBtn {
            width: 35px;
            height:35px;
            background-color: #0a3c5e;
            color: #ffffff;
            float: left;
            margin:5px;
            text-align: center;
            line-height: 35px;
            text-decoration: none;
            border: none;
        }
		#DBFilterBtn:hover {
            background-color: #99cc00;
        }
        #DBFilterBtnActive {
            width: 35px;
            height:35px;
            background-color: #99cc00;
            color: #ffffff;
            float: left;
            margin:5px;
            text-align: center;
            line-height: 35px;
            text-decoration: none;
            border: none;  
        }
    </style>
    
	<p>Filter list by file name</p>
    <script>
		//Set the variable to filter (i.e. Name, Description...)
		filterColumn = "Title";
	
        //Get the current selected letter from URL parameter
        function getParameter(theParameter) { 
          var params = window.location.search.substr(1).split('&');

          for (var i = 0; i < params.length; i++) {
            var p=params[i].split('=');
            if (p[0] == theParameter) {
              return decodeURIComponent(p[1]);
            }
          }
          return false;
        }
        
        //Variable for selected letter 
        var selectedLetter = getParameter('FilterMultiValue');
		
		var alpha = ["A*", "B*", "C*", "D*", "E*", "F*", "G*", "H*", "I*", "J*", "K*", "L*", "M*", "N*", "O*", "P*", "Q*", "R*", "S*", "T*", "U*", "V*", "W*", "X*", "Y*", "Z*"];	
		
		var i = 0; //While loop incrementor
		//Loops through the alphabet array, creating a button for each item (letter). The button is also compared against the 'active' letter, highlighting the relevant button. 
		while (i < 26) {  
			var currentLetter = alpha[i]; //Read from array, using incrementing position.
			var displayLetter = currentLetter.substring(0, currentLetter.length - 1); //Removes the * from the letter
			
			//Check if the current alpha value matches the filter value (from the URL)
			if(currentLetter == selectedLetter){
            document.write('<a href="?FilterName=' + filterColumn + '&FilterMultiValue=' + currentLetter + '" id="DBFilterBtnActive">' + displayLetter + '</a>');
			} else {
				document.write('<a href="?FilterName=' + filterColumn + '&FilterMultiValue=' + currentLetter + '" id="DBFilterBtn">' + displayLetter + '</a>');    
			}
			
			//Increase incrementor
			i++;
		}
    </script>
    <a href="?viewall=1" id="DBFilterBtn">All</a> 
</div>
