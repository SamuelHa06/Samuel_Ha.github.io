[Assignment6.html](https://github.com/user-attachments/files/32986383/Assignment6.html)
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
	    <title>Assignment 6 JavaScript</title>
        <!-- Samuel Ha, Section 38 -->
        <!-- On my honor, I have neither received nor given any unauthorized assistance on this assignment. -->
    </head>
    <body style="background-color:black">
       
        <h1 style="color:yellow">Transportation Alternatives</h1>
        
        <p style="color:limegreen">
            Destination: <input type="text" id="destinationTextbox">
        </p>

        <p style="color:limegreen">
            One-Way <input type="radio" id="oneway" name="trip">
            Round Trip <input type="radio" id="roundtrip" name="trip">
        </p>

        <h2 style="color:limegreen">Transportation Mode Prices and Data</h2>

        <p style="color:limegreen">
            Air: $<input type="text" id="airTextbox">
        </p>

        <p style="color:limegreen">
            Train: $<input type="text" id="trainTextbox">
        </p>

        <p style="color:limegreen">
            Car Data:
            Miles <input type="text" id="milesTextbox">
            Miles per Gallon <input type="text" id="mpgTextbox">
            Price per Gallon: $<input type="text" id="ppgTextbox">
        </p>

        <p>
            <input type="button" value="Process Result" onclick="
            
            // Retrieve input values from textboxes
            var destination = destinationTextbox.value;
            var air = Number(airTextbox.value);
            var train = Number(trainTextbox.value);
            var miles = Number(milesTextbox.value);
            var mpg = Number(mpgTextbox.value);
            var ppg = Number(ppgTextbox.value);

            // Calculate the cost of traveling by car
            var car = (miles / mpg) * ppg;

            // Determine if the trip is one-way or round trip and double the costs for round trip
            var tripType;
            if (oneway.checked) {
                tripType = 'one-way';
            }
            else if (roundtrip.checked) {
                tripType = 'round trip';
                air = air * 2;
                train = train * 2;
                car = car * 2;
            }

            // Compare costs for air, train, and car to find the cheapest option
            var cheapestCost;
            var cheapestMode;
            if (air < train && air < car) {
                cheapestCost = air;
                cheapestMode = 'Air';
            }
            else if (train < air && train < car) {
                cheapestCost = train;
                cheapestMode = 'Train';
            }
            else {
                cheapestCost = car;
                cheapestMode = 'Car';
            }

            // Format the cost to two decimal places with a dollar sign
            var price = '$' + cheapestCost.toFixed(2);

            // Create the final result text
            var result = 'The least expensive ' + tripType + ' transportation mode to ' + destination + ' is by ' + cheapestMode + '. Final price is ' + price;

            // Display the final result text in the result textbox
            resultBox.value = result;">
        </p>

        <p style="color:limegreen">
            Result: <input type="text" id="resultBox" size="90">
        </p>

    </body>
</html>
