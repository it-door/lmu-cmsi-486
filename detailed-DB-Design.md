# Detailed Database Design Document

## 2.1 – Project description, database engine used, potential users, maybe some other stuff

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