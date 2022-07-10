# FetchExercise
My attempt with explanations for FetchRewards' Data Analyst Coding Exercise
The Tools Used are PostgreSQL, Python, PGAdmin4, and Juptyer Notebooks respectively. Any eye-to-screen investigations were done with Visual Studio Code.

## First: Review Existing Unstructured Data and Diagram a New Structured Relational Data Model

For full reference I have never heard of anything called a "joinable key" and any attempts to research it would leave me with the more well-known "primary key" and "foreign key". For the sake of my answers, I assumed that they were equivalent. Another interesting note was the introduction of a data scheme at the bottom of the assignment link. It didn't match the structure of the unstructured data, so I assumed that it's what we wanted the __**end result**__ of the exercise to look like.

The User's Database would be self-explanatory. Every user is uniquely identifiable purely by the userID, thus that serves as the primary key for the table.

Similarly for the Brands Database, everything is uniquely identifiable by some sort of brandID and barcode, where a barcode is different for each version of a product. Sweet Tea 1 is different from Sweet Tea 2 made by the same brand via barcode. Leaving {brandID, barcode} as our primary key for the table

The Reciepts table is only slightly more challenging, everything in the table is uniquely identified by some recieptID which funtionally determines everything else. However, a reciept is identifiable by it's user, date, as well as the items they bought which can functionally determine every other attribute. Our Primary key is {RecieptID}, with our other candidate keys being {userID, purchasedDate, and rewardsRecieptItemList} respectively.

Users has a one-to-many relationship with reciepts
Reciepts have a one-to-many relationship with brands (via barcodes scanned during purchase)
And by proxy, Users has a one-to-many relationships with brands as well, but it's not a required connection.

The Relational Diagram is provided for viewing in the repository.

## Second: Write a query that directly answers a predetermined question from a business stakeholder

## Third: Evaluate Data Quality Issues in the Data Provided

## Fourth: Communicate with Stakeholders

Good Morning, {Client}

This is Christopher Wilson, from the data analyst team. I have started my preliminary investigation of the dataset that you've provided and decided to give it the eye-to-screen test before using any additional tools. I have a few questions that will help determine our most impactful trajectory forward for the company, please answer as best as you can.

- Did we have any plans for the data while collecting it? 
- When did data collection start and when did data collection stop?
