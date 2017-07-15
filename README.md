# Python wrapper for voobly (AOC).

## this project is based on [this](https://code.google.com/archive/p/py-voobly/).

## i made this beacuse python wrapper of 2011 throw me this:

```
IOError: ('http error', 403, 'Forbidden', <httplib.HTTPMessage instance at 0x7f6588b72a70>)
```

I changed urllib for requests, then is required.

    pip install requests

Voobly - a python wrapper for voobly developer api
Voobly is a community driven which allows you to play old direct
play games (like age of empires). Voobly replaces the ZONE service provided by Microsoft, which is not longer available.

The key is available here:
http://www.voobly.com/pages/view/146/Developer-Membership-Types

Usage:

```
>>> voobly = Voobly(voobly_developer_api_key) # 32 bytes long key
>>> voobly_obj.init()
>>> voobly.find_user('some_user')
[{'uid': '12345', 'name': 'some_user'}]
>>> voobly.get_user(12345)
[{'bmonth': '0', 'display_name': 'some_user', 'uid': '12345', 'name': 'some_user', 'level': '0', 'bday': '0', 'byear': '0', 'imagesmall': '/res/user_img_large.png','sex': '0', 'last_login': '0123456789', 'tid': '', 'nationid': 'il', 'nation':'Israel', 'imagelarge': '/res/user_img_small.png', 'account_created': '0123456789'}]
>>> voobly.get_ladder(20)
[{'streak': '0', 'rating': '3359', 'display_name': 'some_user1', 'uid': '12345', 'wins': '682', 'losses': '316', 'rank': '1'},
 {'streak': '0', 'rating': '3206', 'display_name': 'some_user2', 'uid': '54321', 'wins': '351', 'losses': '151', 'rank': '2'},
 {'streak': '0', 'rating': '3205', 'display_name': 'some_user3', 'uid': '111111', 'wins': '351', 'losses': '152', 'rank': '3'},
 ...
 ...
]
>>> voobly.get_ladder(20, start = 1, limit = 2)
[{'streak': '0', 'rating': '3206', 'display_name': 'some_user2', 'uid': '54321', 'wins': '351', 'losses': '151', 'rank': '2'},
 {'streak': '0', 'rating': '3205', 'display_name': 'some_user3', 'uid': '111111', 'wins': '351', 'losses': '152', 'rank': '3'},
]
>>> voobly.get_ladder(20, uidlist = [54321, 111111])
[{'streak': '0', 'rating': '3206', 'display_name': 'some_user2', 'uid': '54321', 'wins': '351', 'losses': '151', 'rank': '2'},
 {'streak': '0', 'rating': '3205', 'display_name': 'some_user3', 'uid': '111111', 'wins': '351', 'losses': '152', 'rank': '3'},
]
>>> voobly.get_ladder(20, uidst = [111111])
[{'streak': '0', 'rating': '3205', 'display_name': 'some_user3', 'uid': '111111', 'wins': '351', 'losses': '152', 'rank': '3'},
]
>>> voobly.find_users(['some_user1', 'some_user2'])
[{'name': 'some_user1', 'uid': '12345'},
 {'name': 'some_user2', 'uid': '54321'},
]
>>> voobly.get_lobbies(13)
[{'lobbyid': '64', 'ladders': ['21', '8', '14', '13'], 'max_players': '1000', 'name': 'Medieval Siege (RM)', 'players_online': '674'},
 {'lobbyid': '67', 'ladders': ['21', '8', '14', '13'], 'max_players': '350', 'name': 'Tours (RM)', 'players_online': '2'},
 ...
 ...
]
```