# CMSI 486 - Ecoins Database
Ted Chu and Tyler Edmiston
Fall 2018
Professor Johnson

## 1.0 Introduction
"Ecoins" are a loyalty point system for LMU's Esports Club. We will be designing a database where we can keep track of our members and their participation in the club with the following:

  - Student [Member] entities with emails and grade levels
  - Events and competitions that take place for or between members
  - "Ecoin" values to said events and competitions
  - A member's "ecoin" balance, based on which events they participated in

## 1.1 Project Description

#### 1.1.01 Database Engine
We are considering using a PostgreSQL database for this project, because it is a standard system that is generally recommended and Tyler has experience with it.
#### 1.1.02 Potential Users
The main goal of this database is to allow Esports **members** to access their "ecoin" balance, but it will also be useful for Esports **administrators** to access members' emails and grade levels in order to keep an active mailing list and organize school-wide competitions and events.
#### 1.1.03 Interface Options
We will probably be developing a simple web-based front-end on the Esports Club's website, https://lmuesports.com/. Members will access their balance by providing their email address.
## 1.2 Data Description
We'll be keeping track of each individual members' ecoin balance, as well as a history of their events and matches. We'll also have member data available for administrators (name, email, grade).
## 1.3 Example Data

## 1.4 Preliminary Schema
| Student | Email | Grade Level | Balance
| ------ | ------ | ------ | ------ |
|  |  | |
|  |  | |
|  |  | |
|  |  | |
|  |  | |
|  |  | |

| Match | Player 1 | Player 2 | Wager | Winner|
| ------ | ------ | ------ | ------ | ------ |
|  |  | |
|  |  | |
|  |  | |
|  |  | |
|  |  | |
|  |  | |

| Event | First Place | Second Place | Third Place
| ------ | ------ | ------ | ------ |
|  |  | |
|  |  | |
|  |  | |
|  |  | |
|  |  | |
|  |  | |

| Event Instance | First | Second | Third | Date
| ------ | ------ | ------ | ------ | ------ |
|  |  | |
|  |  | |
|  |  | |
|  |  | |
|  |  | |
|  |  | |
## 1.5 Preliminary ERD
![ERD][/PrelimERD.png]
