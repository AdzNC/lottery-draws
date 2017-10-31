:# lottery-draws
Lottery Draw Management
=======================

Choice of approach for the Web Service
--------------------------------------
Web API seemed a natural choice as it allows straightforward creation of REST endpoints with a lot of flexibility around routing and binding of input values.

What's outstanding
------------------
Regrettably there's much still left incomplete. Here's summary of what I was planning to do to finish off this project:

*Web Service*
- defining the endpoint routes in App_Start/WebApiConfig.cs;
- testing against the UI;
- Unit Tests.

*UI*
- Define the drawsService in the lotteryDraws module to hold 3 functions which are going to map to endpoint methods on the web service (createDraw, specifyWinningNumbers, searchLotteryDraws).
- Define the event handlers for the 2 navigation and 2 submit buttons on the page. The idea behind the navigation is that the divs show exclusively of each other for the two UI functions on this page (Create Draw and Search Draws).
- Validation needs adding on the UI side for all the user input fields.
- A JavaScript object to hold the Lottery Draw values needs to be populated in the lotteryDrawController in response to a click on btnSaveDraw and then passed into LotteryDrawController.CreateLotteryDraw. In order to map this to an instance of ILotteryDraw I was going to write a custom ModelBinder to make sure that the primary and secondary numbers values are correctly available as List<int> from the JSON values coming into the endpoint.
- For the search by date, I was going to pass the search term down to the web service as a scalar, and parse the returned results to extract the names of the found draws. These would then be displayed to the user in divSearchResults using ngRepeat to iterate over the results.
- Any error conditions returned as a result of the REST calls needs feeding back to the user on the page.
