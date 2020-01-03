# total-comp
Calculates total compensation for any given stock ticker based on the current stock price. Takes in as input company stock symbol, base salary & RSU's. 

The equation is simple:

Total annual comp = `base salary + (0.25 * number_RSUs * value of single RSU)`

Uses the API from https://financialmodelingprep.com/ (thank you!) to look up staock price, then calculates annual total comp. No data leaves the browser except to look up the stock pric data. The calculations are all performed in the browser.

## Example of using the FMP API
```
$(document).ready(function() {
 var url = "https://financialmodelingprep.com/api/v3/company/profile/ORCL";
  $.ajax({
    url: url,
    type: "GET",
    crossDomain: true,
    success: function (response) {  
      console.log(response['profile']['price']);
    },
    error: function (xhr, status) {
      alert("error");
    }
  });
});
```
