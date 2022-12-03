# Project Proposal

## What is the topic of your project?

### "Does any side have an advantage in Dota 2 game?"

Dota 2 is a famous multiplayer online video game and one of the core Esport disciplines.
While the gameplay is too complicated to be described in this project, following information should be sufficient:
1) There are two teams of 5 players competing in the match. Each team protects their base either in bottom-left corner of the map (Radiant side), or in top-right corner (Dire side). Game ends when the main building of any side falls, therefore draw is not possible.
2) In the beginning of the match there's an important phase called "pick", in which players, or team captains, can select so-called "heroes". Hero is a player's in-game character, each having unique stats and abilities. 
3) For public matches, a side of a player, as well as hero pick order, is decided by random at the start of the match.
4) For Pro-tournament matches, the side is decided by a coin flip. Winner of the flip can choose either pick order or a side of their team. Usually teams choose to pick first, leaving the choice of the side to the other team, so this other team is able to adapt in their pick of the side.

From points 3 & 4 a conclusion can be drawn, that for a public match there could be a situation when one team gets both advantageous pick order and side, when for a pro-game that is not possible.

## What are the main issues or problems you plan to address?

Main question would be:

#### Does a Radiant player have a significantly higher win chance than a Dire player, or vice versa?

The question is going to be looked at for pro-matches and for samples of public matches, to find out if there's a difference. 

## What are your plans for obtaining background information (if needed) about your project?

I'm going to use my experience in both playing the game and working in related projects

## Describe the data that you plan on using or collecting, including the variables measured.

There's a project with a data storage of Dota 2 matches and open API called OpenDota:
https://docs.opendota.com/

All data is public by the policies of the game-developer.

The API has the following methods. Field of interest - `radiant_win`

#### GET /proMatches

Allows to get all pro player matches


Response schema: 
```javascript 
[{
    "match_id": 0,
    "duration": 0,
    "start_time": 0,
    "radiant_team_id": 0,
    "radiant_name": "string",
    "dire_team_id": 0,
    "dire_name": "string",
    "leagueid": 0,
    "league_name": "string",
    "series_id": 0,
    "series_type": 0,
    "radiant_score": 0,
    "dire_score": 0,
    "radiant_win": true,
    "radiant": true
}]
```

####  GET /publicMatches

Allows to get a sample of public matches

Response schema: 
```javascript
[{
    "match_id": 0,
    "match_seq_num": 0,
    "radiant_win": true,
    "start_time": 0,
    "duration": 0,
    "radiant_team": "string",
    "dire_team": "string"
}]
```

####  GET /explorer

Allows to run any custom SQL queries over the database


## What questions and/or concerns do you have about your project?
For a long time there's a consensus in the community, that Radiant side has an advantage. 
I am about to find out if that's true, was it ever true, and if there was a moment when it stopped being true.
Additionally, the main question can be answered for different in-game skill groups, to find out if the effect is more noticeable in low-level or high-level matches. 
