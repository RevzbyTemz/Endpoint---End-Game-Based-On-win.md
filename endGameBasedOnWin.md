# Ends a-Game Based On Win
This is the point where a game comes to an end because one of the players has just won. That is, there’s an outright Win. Not when the game is a draw or there’s a tie between players. One example of a win is when one of the players is checkmated, that is, the king is under attack and every move by the king will put it in check. Another example is when an opponent’s time has expired before they’re able to complete a required number of moves. Then there’s a win and that game will come to an end. 


`Method` : PATCH
- This endpoint is for ending a game that has a winner (not for draw)

`Endpoint` : /end

##### Request body
- application/json

#### Parameters 
- Accepts an integer as the user_ID.
- Accepts a string as the game_ID.

```sh
{
  "user_id": 2,
  "game_id": "string"
}
```

##### Sample Request
```bash
curl -X 'PATCH' \
  'https://chess.zuri.chat/api/v1/game/end' \
  -H 'accept: */*' \
  -H 'Content-Type: application/json' \
  -d '{
  "user_id": 2,
  "game_id": "string"
}'
```

#### Sample Response
Code: **200**
- Returns Success. This implies that a game was successfully ended based on win.

Code: **400**
- Returns Bad Request. This implies that the server will not process a request due to an error.

**Response Body**
```sh
{
  "message": "Game does not exist",
  "data": null,
  "success": false
}
```

**Response Headers**
```sh
access-control-allow-origin: * 
 connection: keep-alive 
 content-length: 61 
 content-type: application/json; charset=utf-8 
 date: Tue,21 Sep 2021 10:04:41 GMT 
 etag: W/"3d-geJitolmACn5u3T7flRgtvCftcM" 
 server: nginx/1.21.1 
 x-powered-by: Express 
 ```

Code: **500**
- Returns Error Occurred. This implies an internal server error and something has gone wrong with the server of the website.


#### Request URL 
https://chess.zuri.chat/api/v1/game/end
