# lets-play-a-game

## So this is a multilevel game, where one level leads to another one and you can't finish it without completing the previous one (it contains critical data, like password, or access token, anything)

0. Prerequisites: python3.6, virtualenv, ipython, clone the repo and run `pip install requirements.txt`
1. Quest1: Find the server with zeroconf
2. Quest2: HTTP Request for The Redis Key
3. Quest3: Find Redis Value before time runs out (the key expires in 30 minutes!)
4. Quest4: Fetch document from Mongo / query with aggregates (get the average)
5. Quest5: Light up The Launchpad / MIDI rtmidi
6. Quest6: Ask the corporate client for their input / SOAP, jsonRPC
7. Quest7: Receive the answer with a webhook / create a REST endpoint, do something based on the response you receive
8. Quest8: Down the rabbit hole - use RabbitMQ to process the list of data for your next quest



-----------------------------------------
Tool Development
### Difficulty & Time involvement
4/5, 2 weeks. Extensive architecture required, multiple libraries and components to be used, multiple views
### Description
There is an upcoming coding competition, where students are given a set of coding challenges to use as many technologies as possible. For this to be fair there is a need to track the completion of subsequent challenges.

The key components of the system are:
* leaderboard, showing points achieved and participant's level
* registration, where participants provide their name, and a link to their application
* admin part, allowing to start and stop the competition. Stop automatically shows the winner.
* tracking how much time was spent per user and their assignment
* monitoring task completion with API calls

### Monitoring
* Monitoring/time tracking is done by the background task
  * each registered application is being pinged with HTTP requests
  * each assignment/challenge has a set of URLs which are being used to test if the assignment has been implemented
  * each test should send a JSON message and should receive JSON response in the expected format
