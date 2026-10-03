[Assignment8-1.html](https://github.com/user-attachments/files/32986371/Assignment8-1.html)
<!DOCTYPE html>
    <html>
        <head>
            <meta charset="UTF-8">
            <title>Assignment 8 JavaScript</title>
            <!-- Samuel Ha, Section 38 -->
            <!-- On my honor, I have neither received nor given any unauthorized assistance on this assignment. -->
        </head>
        <body>
            <script>
                // Set up arrays with my own numbers
                var teams = ["Reds", "Greens", "Blues", "Purples"];
                var gamesWon = [2, 1, 0, 6];
                var gamesTied = [3, 3, 4, 2];
                var gamesLost = [4, 5, 5, 1];
                var goalsScored = [3, 7, 2, 9];
                var goalsReceived = [5, 1, 8, 4];

                // Variable for total games required
                var totalGamesRequired = 9;

                //Function for verification of total number of games
                function verifyGames(won, tied, lost, totalReq) {
                    for (var i = 0; i < teams.length; i++) {
                        if (won[i] + tied[i] + lost[i] !== totalReq) {
                            document.write("ERROR: Total number of games played by " + teams[i] + " is not 9.");
                            return false;
                        }
                    }
                    return true;
                }

                // Function for calculation of total points
                function Points(teams, won, tied) {
                    document.write("<h3>Total Points For Each Team</h3>");
                    for (var i = 0; i < teams.length; i++) {
                        var points = 3 * won[i] + 1 * tied[i];
                        document.write(teams[i] + ": " + points + "<br>");
                    }
                    document.write("<hr>");
                }

                // Function for calculation of goals difference
                function goalsDifference(teams, scored, received) {
                    document.write("<h3>Goals Difference For Each Team</h3>");
                    for (var i = 0; i < teams.length; i++) {
                        var diff = scored[i] - received[i];
                        document.write(teams[i] + ": " + diff + "<br>");
                    }
                    document.write("<hr>");
                }

                // Function for performance
                function Performance(teams, won, tied, lost) {
                    document.write("<h3>Performance For Each Team</h3>");
                    for (var i = 0; i < teams.length; i++) {
                        var totalPlayed = won[i] + tied[i] + lost[i];
                        var perf = (won[i] / totalPlayed) * 100;
                        document.write(teams[i] + ": " + perf.toFixed(0) + "%<br>");
                    }
                    document.write("<hr>");
                }

                // Function for bar chart
                function barChart(teams, won, tied) {
                    document.write("<h3>Bar Chart For Each Team (shows total points)</h3>");
                    for (var i = 0; i < teams.length; i++) {
                        var points = 3 * won[i] + tied[i];
                        var stars = "";
                        for (var j = 0; j < points; j++) {
                            stars += "*";
                        }
                        document.write(teams[i] + ": " + stars + "<br>");
                    }
                }

                //  If statement for the final result
                if (verifyGames(gamesWon, gamesTied, gamesLost, totalGamesRequired)) {

                    document.write("<h1><b>Soccer Tournament Results</b></h1>");

                    var today = new Date();
                    
                    document.write("<i><b>Report Date: " + today + "</b></i><br><br>");

                    Points(teams, gamesWon, gamesTied);
                    
                    goalsDifference(teams, goalsScored, goalsReceived);
                    Performance(teams, gamesWon, gamesTied, gamesLost);
                    barChart(teams, gamesWon, gamesTied);
                }
            </script>
        </body>
    </html>
