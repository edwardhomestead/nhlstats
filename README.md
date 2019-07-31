# nhlstats
A C# .NET Standard Library for interfacing with the open NHL Stats API.

Current APIs that this library exposes as C# API endpoints include:

## Schedule

### Schedule Class Properties
VARIABLE NAME | VARIABLE TYPE | Description | Example 
--------------|---------------|-------------|--------
totalItems|string|The number of total items in the Schedule for a specific date.|2
totalEvents|string|The number of total events in the Schedule for a specific date.|0
totalGames|string|The number of total games in the Schedule for a specific date.|12
totalMatches|string|The number of total matches in the Schedule for a specific date.|1
season|string|The season that the Schedule gameDate resides in.|20192020
scheduleDate|string|The date for the data that theSchedule class is holding.|2019-05-31
games|List < Game >|A list of Game objects (see below for definition) that reside in the schedule for a given date.|(see definition for Game class)
scheduleJson|JObject|The JSON output returned by the NHL API for the API call.|(JSON Data)

### Schedule Class Methods
METHOD NAME | Input Variable(s) | Output
------------|-------------------|-------
Schedule() | NONE | Creates a Schedule object for today's date
Schedule(string gameDate) | gameDate (string) -> FORMAT:  YYYY-MM-DD | Creates a schedule object for date specified in gameDate
static List< string > GetListOfGameIDs(string gameDate) | gameDate (string) -> FORMAT:  YYYY-MM-DD | Static method that brings back a list of Game IDs for date specified in gameDate 


## Game

### Game Class Properties
VARIABLE NAME | VARIABLE TYPE | Description | Example 
--------------|---------------|-------------|--------
gameID|string|The Game ID returned by the NHL API call.|2018021169
gameLink|string|URL of the writeup for the game.|https://statsapi.web.nhl.com/api/v1/game/201502093
gameType|string|Denotes the type of game (R=Regular; A=All Star; PR=Preseason; P=Playoff)|PR
season|string|The season that the Game resides in.|20192020
gameDate|string|The date of the game in the format YYYY-MM-DD|2019-03-25
abstractGameState|string|The state of the game.|Final
codedGameState|string|A number denoting the Game state.|7
detailedState|string|Unknown|???
statusCode|string|Status Code for the game.  May have the same value as codedGameState.|7
homeTeam|Team|The Team object holding data on the Home Team.|(see definition for Team class)
awayTeam|Team|The Team object holding data on the Away Team.|(see definition for Team class)
gameVenue|Venue|The Venue object holding data on the game Venue.|(see definition for Venue class)
gameContent|GameContent|The GameContent object holding data for the game content.|(see definition for GameContent class)
gameParticipants|List < Player >|The List of players that participated in the game.|(see definition for Player class)
gameEvents|List < GameEvents >|The List of game events that occurred during the game.|(see definition for GameEvents class)
periodData|List < Period >|The List of period data for the game.|(see definition for Period class)
gameBoxScore|BoxScore|The data that holds the box score statistics for the game.|(see definition for BoxScore class)
gameJson|JObject|The JSON output returned by the NHL API for the API call.|(JSON Data)

### Game Class Methods
METHOD NAME | Input Variable(s) | Output
------------|-------------------|-------
Game() | NONE | Creates an empty Game object.
Game(string theGameID) | theGameID (string) | Populates a Game object with data corresponding to the input Game ID.
Game(string theGameID, int featureFlag) | theGameID (string) ; featureFlag (int) | DEPRECATED; NOT BEING MAINTAINED.

## GameContent

### GameContent Class Properties
VARIABLE NAME | VARIABLE TYPE | Description | Example 
--------------|---------------|-------------|--------
gameID|string|The unique identifier for the Game. |2018020245
previewTitle|string|The preview summary title for the Game.|Toronto Maple Leafs Boston Bruins game preview
previewHeadline|string|The headline for the preview of the Game.|Maple Leafs at Bruins preview
previewSubHead|string|The sub-headline for the preview of the Game.|Toronto can tie its record for longest road win streak to begin season; Halak to start for Boston
previewSeoDescription|string|The search engine-optimized description for the Game.|Toronto can tie its record for longest road win streak to begin season; Halak to start for Boston
previewUrl|string|The URL for the preview article.|http://www.nhl.com/news/toronto-maple-leafs-boston-bruins-game-preview/c-301798978?game_pk=2018020245
previewMediaPhoto2568x1444|string|The URL for the preview photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301799740/2568x1444/cut.jpg
previewMediaPhoto2208x1242|string|The URL for the preview photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301799740/2208x1242/cut.jpg
previewMediaPhoto2048x1152|string|The URL for the preview photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301799740/2048x1152/cut.jpg
previewMediaPhoto1536x864|string|The URL for the preview photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301799740/1536x864/cut.jpg
previewMediaPhoto1284x722|string|The URL for the preview photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301799740/1284x722/cut.jpg
previewMediaPhoto1136x640|string|The URL for the preview photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301799740/1136x640/cut.jpg
previewMediaPhoto1024x576|string|The URL for the preview photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301799740/1024x576/cut.jpg
previewMediaPhoto960x540|string|The URL for the preview photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301799740/960x540/cut.jpg
previewMediaPhoto768x432|string|The URL for the preview photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301799740/768x432/cut.jpg
previewMediaPhoto640x360|string|The URL for the preview photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301799740/640x360/cut.jpg
previewMediaPhoto568x320|string|The URL for the preview photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301799740/568x320/cut.jpg
previewMediaPhoto372x210|string|The URL for the preview photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301799740/372x210/cut.jpg
previewMediaPhoto320x180|string|The URL for the preview photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301799740/320x180/cut.jpg
previewMediaPhoto248x140|string|The URL for the preview photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301799740/248x140/cut.jpg
previewMediaPhoto124x70|string|The URL for the preview photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301799740/124x70/cut.jpg
gameContentJson|JObject|The JSON output returned by the NHL API for the API call.|(JSON Data)
recapTitle|string|The title of the recap article for the game.|Toronto Maple Leafs Boston Bruins Game Recap
recapHeadline|string|The headline of the recap article for the game.|Pastrnak gets hat trick, Bruins send Maple Leafs to first road loss
recapSubHead|string|The sub-headline of the recap article for the game.|Forward has third four-point game of season; Halak makes 40 saves
recapSeoDescription|string|The search engine-optimized description of the article for the game.|BOSTON -- David Pastrnak scored his third NHL hat trick to help the Boston Bruins hand the Toronto Maple Leafs their first road loss of the season, 5-1 at TD Garden on Saturday.
recapUrl|string|The URL to the recap article for the game.|http://www.nhl.com/news/toronto-maple-leafs-boston-bruins-game-recap/c-301799398?game_pk=2018020245
recapMediaPhoto2568x1444|string|The URL for the recap photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301820386/2568x1444/cut.jpg
recapMediaPhoto2208x1242|string|The URL for the recap photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301820386/2208x1242/cut.jpg
recapMediaPhoto2048x1152|string|The URL for the recap photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301820386/2048x1152/cut.jpg
recapMediaPhoto1704x960|string|The URL for the recap photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301820386/1704x960/cut.jpg
recapMediaPhoto1536x864|string|The URL for the recap photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301820386/1536x864/cut.jpg
recapMediaPhoto1284x722|string|The URL for the recap photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301820386/1284x722/cut.jpg
recapMediaPhoto1136x640|string|The URL for the recap photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301820386/1136x640/cut.jpg
recapMediaPhoto1024x576|string|The URL for the recap photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301820386/1024x576/cut.jpg
recapMediaPhoto960x540|string|The URL for the recap photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301820386/960x540/cut.jpg
recapMediaPhoto768x432|string|The URL for the recap photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301820386/768x432/cut.jpg
recapMediaPhoto640x360|string|The URL for the recap photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301820386/640x360/cut.jpg
recapMediaPhoto568x320|string|The URL for the recap photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301820386/568x320/cut.jpg
recapMediaPhoto372x210|string|The URL for the recap photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301820386/372x210/cut.jpg
recapMediaPhoto320x180|string|The URL for the recap photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301820386/320x180/cut.jpg
recapMediaPhoto248x140|string|The URL for the recap photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301820386/248x140/cut.jpg
recapMediaPhoto124x70|string|The URL for the recap photo of the resolution defined in the name of this property.|https://nhl.bamcontent.com/images/photos/301820386/124x70/cut.jpg
recapPlaybackFLASH_192K_320X180|string|The URL to the recap video of the resolution defined in the name of this property.  Currently not being populated.|N/A
recapPlaybackFLASH_450K_400X224|string|The URL to the recap video of the resolution defined in the name of this property.  Currently not being populated.|N/A
recapPlaybackFLASH_192K_320X180|string|The URL to the recap video of the resolution defined in the name of this property.  Currently not being populated.|N/A
recapPlaybackFLASH_1200K_640X360|string|The URL to the recap video of the resolution defined in the name of this property.  Currently not being populated.|N/A
recapPlaybackFLASH_1800K_960X540|string|The URL to the recap video of the resolution defined in the name of this property.  Currently not being populated.|N/A

### GameContent Class Methods
METHOD NAME | Input Variable(s) | Output
------------|-------------------|-------
GameContent() | NONE | Creates an empty GameContent object.
GameContent(string theGameID)|theGameID (string)|Populates a GameContent object for the Game denoted by ID theGameID.

## GameEvents

### GameEvent Class Properties
VARIABLE NAME | VARIABLE TYPE | Description | Example 
--------------|---------------|-------------|--------
correspondingGameID |string|The Game ID of the game that the GameEvent occurred.|2018020251
eventType|string|The type of the Event.|Giveaway
eventCode|string|The event code of the GameEvent.|CBJ15
eventTypeID|string|The ID of the event type for the GameEvent.|GIVEAWAY
eventDescription|string|The description of the GameEvent.|Giveaway by Vladislav Namestnikov
eventSecondaryType|string|The secondary type of the GameEvent.  Appears not to be used at present.|N/A
eventIDx|string|The eventIDx of the GameEvent.  I am not sure what this corresponds to.|21
eventID|string|The event ID for the GameEvent. Please note that this is not unique across all games.|15
period|string|The period number that the GameEvent occurred in.|1
periodType|string|The type of period the GameEvent occurred in.|REGULAR
ordinalPeriodNumber|string|The ordinal number of the period that the GameEvent occurred in.|1st
periodTime|string|The time in the period that the GameEvent occurred at.|3:15
periodTimeRemaining|string|The time remaining in the period that the GameEvent occurred at.|16:45
dateTimeStamp|string|The datetime stamp for the GameEvent when it occurred. I believe this time stamp is in the Greenwich Mean Time timezone.|2018-11-11 00:13:46.000
goalsAway|string|The number of goals for the away team at the time of the GameEvent.|0
goalsHome|string|The number of goals for the away team at the time of the GameEvent.|0
xCoordinate|string|The x-coordinate on the ice that the GameEvent occurred.  Range is between -100 and 100 (ends of the boards)|55.00
yCoordinate|string|The y-coordinate on the ice that the GameEvent occurred.  Range is between -100 and 100 (sides of the boards)|-40.00
team|Team|The Team object holding the data on which team initiated the GameEvent.|(see definition for Team class)
players|List < Player >|The list of Players involved in the GameEvent.|(see definition for Player class)
gameEventJson|JObject|The JSON output returned by the NHL API for the API call.|(JSON Data)

### GameEvent Class Methods
METHOD NAME | Input Variable(s) | Output
------------|-------------------|-------
GameEvent() | NONE | Creates an empty GameEvent object.
GameEvent(JToken jsonGameEvents)|jsonGameEvents (JToken)| Populates a GameEvent object with the data from the JSON JToken.  NOTE:  This JToken is taken from the JSON within the Game JSON document.

## Team

### Team Class Properties
VARIABLE NAME | VARIABLE TYPE | Description | Example 
--------------|---------------|-------------|--------
NHLTeamID | int | The Team ID for a team. | 12
TeamName | string | The name of the team. | Hurricanes
TeamCity | string | The city/geographical area that the team resides in. | Carolina
TeamAbbreviation | string | The abbreviation code for the team. | CAR
TeamVenue | Venue | The Venue object that contains data for the team's home venue. | (see definition for Venue class)
FirstYearOfPlay | string | The inaugural year for the team entering the NHL. | 1979
teamDivision | Divsion | The Division object holding info on the division the team resides in. | (see definition for Division class)
teamConference | Conference | The Conference object holding info on the conference the team resides in. | (see definition for Conference class)
webSite | string | The website URL address for the team's homepage. | http://www.carolinahurricanes.com/
Wins | int | The team's number of wins in the current season. | 46
Losses | int | The team's number of losses in the current season. | 31
OvertimeLosses | int | The team's number of losses in overtime. | 5
GoalsScored | int | The team's current number of goals scored this season. | 132
GoalsAgainst | int | The team's current number of goals against this season. | 128
Points | int | The current number of points the team has this season. | 97
DivisionRank | int | The current rank of the team within its Division this season. | 2
ConferenceRank | int | The current rank of the team within its Conference this season. | 6
LeagueRank | int | The current rank of the team within the entire league this season. | 11
WildcardRank | int | The current Wildcard rank of the team within the conference this season.  | 2
ROW | int | The current number of wins of the team in regulation and overtime combined. | 42
GamesPlayed | int | The number of games the team has played so far in the current season. | 81
StreakType | string | The type of streak that the team is currently on. | L
StreakNumber | int | The number of games for the team's current streak. | 3
StreakCode | string | The coded streak description for the team's current streak. | L3
LastUpdated | string | The datetime that the team data was last updated on by the NHL API. | 2019-05-11 4:39:48AM
teamJson | JObject | The JSON output returned by the NHL API for the API call.|(JSON Data)

### Team Class Methods
METHOD NAME | Input Variable(s) | Output
------------|-------------------|-------
Team() | NONE | Creates an empty Team object.
Team(string teamID) | teamID (string) | Creates a Team object populated with data for the team specified by teamID.
Team(string teamID, int featureFlag) | teamID (string) ; featureFlag (int) | DEPRECATED; NOT BEING MAINTAINED.
static List < Team > GetAllTeams() | NONE | Static method that returns a list of all teams within the league; output is of type List < Team >.

## Venue

### Venue Class Properties
VARIABLE NAME | VARIABLE TYPE | Description | Example 
--------------|---------------|-------------|--------
venueID | string | The Venue ID for a venue. | 5034
venueName | string | The name of the venue. | PPG Paints Arena
venueJSON | JObject | The JSON output returned by the NHL API for the API call.|(JSON Data)

### Venue Class Methods
METHOD NAME | Input Variable(s) | Output
------------|-------------------|-------
Venue() | NONE | Creates an empty Venue object.
Venue(string theVenueID) | string theVenueID | A Venue object populated with the data for a venue with a Venue ID of theVenueID.

## Division

### Division Class Properties
VARIABLE NAME | VARIABLE TYPE | Description | Example 
--------------|---------------|-------------|--------
divisionId | int | The ID for a Division. | 15
divisionName | string | The name of the Division. | Pacific
shortName | string | The short name of the Division. | PAC
abbreviation | string | The abbreviation of the Division. | P
conference | Conference | An object holding the Conference data for the Division. | (see definition for Conference class)
active | string | Whether the Division is active or not. | True
divisionJSON | JObject | The JSON output returned by the NHL API for the API call.|(JSON Data)

### Division Class Methods
METHOD NAME | Input Variable(s) | Output
------------|-------------------|-------
Division() | NONE | Creates an empty Division object.
Division(int theDivisionId) | theDivisionId (int) | Returns a Division object populated with data for the Division with ID theDivisionId.
static List < Division > GetAllDivisions() | NONE | Returns a List < Division > with all Divisions.
