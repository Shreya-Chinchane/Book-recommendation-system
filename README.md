# Book-recommendation-system

In this Book recommendation system, different models are used for recommending relevant books to the user. They are-
* content-based
* collaborative-based
* K nearest neighbour based
* hybrid filtering


The dataset used in this work is the Book-Crossing Dataset that comprises three tables: -
* Books:  It has 8 columns; ISBN, Book title, Book author, Year of publication, Publisher, and three columns for Book cover Image URLs representing three different versions (small, medium, and large).
* Users:  Contains the user’s information. It consists of 3 columns: UserID, Location, and age.
* Ratings:  Contains the information on ratings of the books. It consists of 3 columns UserID, ISBN, and Book Rating.

# All the pre-processing and cleaning on the dataset is described below:

* Books Table
1. Drop all three Image URL features.
2. Check for the number of null values in each column. There are only 3 null values in the table. Replace these three empty cells with ‘Other’.
3. Check for the unique years of publications. Two values in the year column are publishers. Also, three tuples have the name of the author of the book merged with the title of the book.
4. Manually set the values for these three above obtained tuples for each of their features using the ISBN number of the book.
5. Convert the type of the years of publications feature to the integer.
6. By keeping the range of valid years as less than 2022 and obviously not 0, replace all invalid years with the mode of the publications that is 2002.
7. Upper-casing all the alphabets present in the ISBN column and removal of duplicate rows from the table.

* Users Table
1. Check for null values in the table. The Age column has more than 1 lakh null values.
2. Check for unique values present in the Age column. There are many invalid ages present like 0 or 244.
3. By keeping the valid age range of readers as 10 to 80, replace null values and invalid ages in the Age column with the mean of valid ages.
4. Removal of duplicate entries from the table.

* Ratings Table
1. Check for null values in the table.
2. Check for the Rating column and User-ID column to be an integer.
3. Removal of punctuation from ISBN column values and if that resulting ISBN is available in the book dataset only then consider dropping that entity.
4. Upper-casing all the alphabets present in the ISBN column.
5. Removal of duplicate entries from the table.

* Merging of all three Tables
Merging Books, Users and Rating Tables in One dataset.
