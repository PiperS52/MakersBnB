# MakersBnB

[![Build Status](https://travis-ci.com/ZeenLamDev/MakersBnB.svg?branch=master)](https://travis-ci.com/ZeenLamDev/MakersBnB)

## Code style
[![Ruby Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://github.com/testdouble/standard)

## Brief

This was a group project as part of Makers Academy, with the purpose to create a web app that allows users to list spaces they have available, and to hire spaces for the night.

## User Stories

```
1.  As a user
    So I can use MakersBnB
    I would like to sign up

2.  As a user
    So I can make changes to my bookings/listings
    I would like to log in

3.  As a user
    So I can protect my bookings/listings
    I would like to log out

4.  As a user
    So I can choose a space
    I would like to see a list of spaces

5.  As a user
    So I can see spaces in a specified date range
    I would like to be able to filter the list by date of availibility.

6.  As a owner
    So I could rent out a space
    I would like to list a space.

7.  As a owner
    So I could rent out multiple spaces
    I would like to list multiple spaces

8.  As a owner
    So I can give details of my space
    I would like to provide a name, description & price per night

9.  As a owner
    So I can manage availability
    I would like to be able to offer a range of available dates

10. As a user
    So that I can rent an owners space
    I would like to be able to request an owners space for one night

11. As a owner
    So I can approve a booking
    I would like to be able to approve bookings on my space

12. As a user
    So spaces don't get double booked
    It should not allow me to book a date that has already been booked

13. As an owner
    Until I confirm a booking
    It should still be available
```

## Technologies used

Ruby, RSpec, Sinatra, Capybara, PostgreSQL

## Getting Started

Clone the repository from GitHub:
```
$ git clone https://github.com/PiperS52/MakersBnB.git
$ cd MakersBnB
```
Load the dependencies:
```
$ bundle install
```
Create a new database with tables in psql:
```
$ psql postgres;

CREATE DATABASE makersbnb;
CREATE TABLE users (id SERIAL PRIMARY KEY, email VARCHAR(120), password VARCHAR(120), username VARCHAR(120));
CREATE TABLE spaces (id SERIAL PRIMARY KEY, name VARCHAR(60), description VARCHAR(240), price INTEGER, date_available_from DATE, date_available_to DATE, owner_id INTEGER REFERENCES users(id));
CREATE TABLE requests (id SERIAL PRIMARY KEY, requester_id INTEGER REFERENCES users(id), requested_date date, space_id INTEGER REFERENCES spaces(id), status VARCHAR(100));
```
Complete above steps for `CREATE DATABASE makersbnb_test;`

Run the server:
```
$ rackup
```
visit http://localhost:9292/

## Contributions

Many thanks to the rest of the MakersBnB team:<br/>
[Zeen Lam](https://github.com/ZeenLamDev), [Aman Tank](https://github.com/AmanTank187), and [Chris Whitehouse](https://github.com/chriswhitehouse)
