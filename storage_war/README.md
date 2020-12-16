# STORAGE WAR

## INTRODUCTION 

* Storage war is an auction game played by two to 4 players. In the game, players will try to rival each other by bidding the most profitable storage, and try to become the richest 
player by end of 10 rounds of bidding exercises.

## CONCEPT OF THE GAME 

* When rent is not paid on a storage locker for three months, the contents can be sold by an auctioneer as a single lot of items in the form of a cash-only auction. Storage warrior 
who visit storage facilities will bid on these lockers. Before each locker is auctioned, the buyers are given tips to access the possible value of the storage items. 

## GAME PLAY

* At the start of a new game, each player will be given a $5,000 dollars in the bank. Before the start of each biding exercise, each player will be given a brief introduction of the 
storage that they will be bidding and following up a quick tip flash. Each player supposes to make a quick judgement if the storage is worth bidding for. 

* After the start of the bidding exercise, a timer will start to countdown from 90 seconds. Within the 90 seconds, there may be up to 3 news flash that may hint if the storage has 
valuable item in. Therefore, each player will have to make their best judgement with the available information.

* After the bidding has ended, a final news flash will be released to inform all the players on the actual market price of the storage items. The storage items will then be sold back 
to the bank. If a player has won the bid, the bank will credit the profit or deduct the losses from the player account.

## AUCTION PLAY

* There will be a minimum bidding price set by the game at the start of the auction. All players are eligible to bid for the storage as long as their bank account needs the minimum bid 
requirement. Players can also choose not to bid in the auction.

* All players will begin their bid by bidding the minimum bidding price set by the game. Subsequently, all bidding will be incremental by $50. If a player can choose to bid more than 
the incremental value of $50, however, the auction board will only show the last bidding price plus $50. The system will then keep the player’s highest bidding value as a reserved 
price. The reserved price will only made know to the player that place the bid. For example, if the player A decides to bid $1,500 dollars on a minimum bid value of $1,000 of a 
storage, the auction board will only show player A bidding price is $1,050. If player B decided to bid $1,200, the system will automatic show the highest bidder is still Player A 
at $1,250; bidding is incremental by $t0. The process will go on until other player bid above $1,500.  

## END OF GAME

* There will be 10 rounds of auction events. At the end of the 10 rounds of auction, the players with the most money in the bank will declare the winner and conferred 
as a “STORAGE WARRIOR”.

## Storage War sample Mongo Collections

* There are 3 collections setup for this game. They are:

  Hall of Fame : To display the Top 5 winners by their winning amount. 
   Player_name (to display the player name)
   Fund (to display their recorded winning)

   {"_id":{"$oid":"5fd9a6fbe41de4d902c81140"},"player_name":"","fund":""}

  Players database : To register player_name in the game
  Player_name (To register the player name)
  Fund (This is automatically assigned by the system. The inital amount is $5000)

  {"_id":{"$oid":"5fd9a729e41de4d902c81141"},"player_name":"","fund":"5000"}

  Auction database : During the auction, we need to display the initial "auction_price". As we start to receive bidding, we need to have "bidding_price data. Some players 
  may bid higher than the incremental price, any amount higher than the incremental price ($500 in this game), it will be store in the reserved_price. At the end of the auction
  an actual price will be made known to the bidding. The player will then know if they have make any profit from it. The difference will be display in their fund. A "timer" is to
  start the counter. Lastly, up to 4 tips may be displayed to hint to the players of the possible values of the storage.

  Auction Name : The name of the storage. 
  Auction Price : The inital starting price
  Actual Price : The actual price of the storage
  Bidding Price : Price bids by the player
  Reserved Price : Price bids by the player
  Timer : 90 second bidding
  Tip 1 - 4 :To give hint to players.

 {"_id":{"$oid":"5fd9a74be41de4d902c81142"},"auction_name":"","auction_price":"","actual_price":"","bidding_price":"","reserved_price":"",
"timer":"","tip_1":"","tip_2":"","tip_3":"","tip_4":""}