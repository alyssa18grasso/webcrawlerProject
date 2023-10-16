## APPROACH
Our approach to implementing this code was to start with the login, which meant that we had to implement the methods get and post in our Crawler. For the login, we would send a GET request to the login page to get the CSRF and middleware token, and then send a POST request using those fields to login into FakeBook. When a 302 status code is returned, we send the same request as a GET request to get to the home page. Immediately we parse to get a list of links to follow, and then begin the crawling processor. We use a loop for the crawler, and to avoid getting caught in an infinite loop, we used a dictionary to keep track of all pages we have visited/need to visit.

## CHALLENGES
The challenges we approached was setting up our loop correctly, since we had to keep track of both visited and unvisited pages. Our solution was to create a dictionary of visited pages. If a new page was detected with the HTML parser, it was added to the dictionary with a default value of False. When a page is parsed, its value is set to True. Pages whose value are set to False are popped out of the dictionary temporarily during the crawling phase.

Another challenge was the 

## TESTS
To test our code, we ran the code locally to verify that we were getting the correct flags, and ran the code on Gradescope to confirm that it passed performance tests.
