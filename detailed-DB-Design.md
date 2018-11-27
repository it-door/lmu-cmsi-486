# Detailed Database Design Document

## 2.1 – Project Description
"Ecoins" are a loyalty point system for LMU's Esports Club. This is a database where we can keep track of our members and their participation in the club.
The main goal of this database is to allow Esports **members** to access their "Ecoin" balance, but it will also be useful for Esports **administrators** to access members' emails and grade levels in order to keep an active mailing list and organize school-wide competitions and events.

This project implements a PostgreSQL database.
## 2.2 – Data Dictionary

- Member Table
  - name: full name of the member
  - email: school email of the member, primary key
  - grade level: current grade for the user (1, 2, 3, or 4)
  - balance: current Ecoin balance

- Match Table
  - matchID: unique identifier for match, primary key
  - player1: one of the two players in the match, foreign key
  - player2: second player in the match, foreign key
  - wager: Ecoin amount waged for the match
  - winner: unique identifier for the winning player, foreign key

- Event Type Table
  - EventName: unique identifying name for an event type, primary key
  - firstPlace: Ecoin amount to be rewarded for winning first place
  - secondPlace: Ecoin amount to be rewarded for winning second place
  - thirdPlace: Ecoin amount to be rewarded for winning third place

- Event Instance Table
  - InstanceID: unique identifier for instance of an event, primary key
  - EventType: identifier relating back to Event Type, foreign key
  - first: the first-place winner of event instance, foreign key
  - second: the second-place winner of event instance, foreign key
  - third: the third-place winner of event instance, foreign key
  - date: date information for when the event takes place

## 2.3 – Finalized Entity-Relationship Diagram

![ERD](/images/detailed-ERD.png)

## 2.4 – Sample Queries
 - Providing an email and getting a balance in return.
 
 ```
 SELECT balance
FROM "Member"
WHERE email LIKE 'azapataa@lion.lmu.edu'
```

 - Providing a match and returning the match details, including both players, wager, and winner.

```
SELECT description, player1, player2, winner, wager
FROM "Match"
WHERE "matchID" = 3
```

 - Providing an event name and returning the associated winnings with first second and third.

 ```
SELECT * 
FROM "Event Type"
WHERE "EventName" LIKE 'Garfield%'
 ```
 - Providing an event instance and returning the winners.
 ```
 SELECT description, player1, player2, winner, wager
FROM "Match"
WHERE "description" LIKE 'DDR%'
```
 - Providing an email and returning event instances that person has participated in. 
 ```
 SELECT "EventName"
FROM "Event Instance"
WHERE 'thiggin6@lion.lmu.edu' IN(first, second, third)
```