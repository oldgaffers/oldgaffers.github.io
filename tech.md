# Boat Register Technology

## Background

The OGA Boat Register is intended to be a complete solution to curating and presenting members boats and other boats of significance.

This iteration is at least the fourth electronic database of boats used by the OGA.

The first one may have been the one created by Dick Dawson on a PC, probably in the late 1990s.

The first version I was involved with was created for the East Coast Area by Steve Daly-Yates with some help in schema design from myself and others.

This evolved into the pan-OGA database integrated into the main OGA website's database and implemented in Drupal 7.

The new version is intended to support all the information in the previous version and to allow additional data to be supported in future. Whilst primarily designed for the OGA, the new database is capable of being replicated by other organisations and is developed with that in mind.

## Overall structure

It is easier to discuss the requirements and design in parts and the overall architecture forms a natural partitioning.

The Boat Register consists of four main components. The database, an API layer, a web front-end for users and another web front end for boat register editors. There are additional helper components such as authorisation and authentication.

## Overall Requirements

The Boat Register gets used for three main purposes

1. A historical record of leisure and working craft
2. A means for members to buy and sell boats
3. A resource for race officers needing handicaps for participating vessels

As a historical record it is also used for recreational and social networking to find a boat seen on the water or to put people in contact who have a shated interest in a boat, or a designer or class of boats. Photographs are an important part of it.

## Technical Details

### The database

The database is a standard relational database. Some compromise has been made to de-normalise the schema to work within the constraints of the free tier within Heroku which has a limit of 10,000 records. As we have around 4,000 boats this works well but forces most of the data for a boat to live within a single record. This is alleviated by making some highly structured fields like handicap data JSON objects within the main table, giving it some of the characteristics of a no-sql document store.

Images are not stored in the database but in a separate SmugMug account.

### The API

The API has been developed using GraphQL. There are many ways to develop a GraphQL schema and the Boat Register uses Hasura, a database schema first approach which creates the API automatically from the database schema. This gives it a somewhat 'SQL-like' interface which is rich but not as clean as an API-first approach would provide.

The Hasura dashboard is deployed in a free application on Heroku and this incorporates the database.

One great benefit of this approach is the very fine-grained access control supported by Hasura which avoids the need for the user frontend to implement any security mechanisms, at least until we allow logged-in members to access ownership details.

### The User Front end

The user front-end is a React single page application hosted on Github Pages. It is accessed as an iframe withing the main OGA site which has some significant disadvantages.

### The Editor Frontend

We haven't done this yet.
