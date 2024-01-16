<!DOCTYPE html>
<html lang="en">

<head>
    <meta http-equiv="Content-Security-Policy" content="trusted-types 'default'">

    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fin.India Holdings MF Stock Price Ribbon and Consumer Chat24/7. Invest Now!!! Subscribe Now!!!</title>
    <script src="https://code.jquery.com/jquery-3.6.4.min.js"></script>

    <style>
        @import url('first-stylesheet.css');
        @import url('second-stylesheet.css');

        #stockRibbonContainer,
        #chatContainer {
            width: 100%;
            overflow: hidden;
        }

        #stockRibbon,
        .chat-window {
            overflow: hidden;
            white-space: nowrap;
        }

        .chat-window {
            margin-top: 20px;
        }

        body {
            font-family: 'Arial', sans-serif;
            background-color: #f0f0f0;
            color: #333;
        }
    </style>

</head>

<body>

    <div id="stockRibbon" style="overflow: hidden; white-space: nowrap;"></div>

    <script>
        $(document).ready(function () {
            // Your code to fetch stock data and update the ribbon
            updateStockRibbon();
            // Update stock prices every 60 seconds (adjust as needed)
            setInterval(updateStockRibbon, 60000);
        });

        function updateStockRibbon() {
            // Replace these symbols with the stocks you are interested in
            const stockSymbols = ['AAPL', 'GOOGL', 'MSFT', 'AMZN'];

            // Clear existing content
            $('#stockRibbon').empty();

            // Fetch stock data for each symbol
            stockSymbols.forEach(symbol => {
                $.ajax({
                    url: `https://www.google.com/finance/quote/${symbol}:GOOG`,
                    dataType: 'html',
                    success: function (data) {
                        // Extract stock price from the fetched HTML (Note: This is hypothetical)
                        const stockPrice = $(data).find('.class-for-stock-price').text().trim();

                        // Create a div element for each stock
                        const stockDiv = $('<div>').text(`${symbol}: ${stockPrice}`).css('padding', '10px');

                        // Append the stock div to the ribbon
                        $('#stockRibbon').append(stockDiv);
                    },
                    error: function (xhr, status, error) {
                        console.error(`Failed to fetch data for ${symbol}: ${error}`);
                    }
                });
            });
        }
    </script>
    <button type="button" role="button" aria-label="Close">X</button>
</body>

</html>
