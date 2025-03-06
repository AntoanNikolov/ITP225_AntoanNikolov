## Many-to-Many Overview (5:34)
- example: one book can have many authors & one author can have many books

## A Simple Many-To-Many Example in Django (12:35)
- a many to many relationship is broken into two one-to-many relationships with a junction table between them
- django hides the junction table
- the junction tabe contains the foreign keys to each model. The models establish their many-to-many relationship by relating to that value in the junction table
- JunctionTable(book=b1, author=a1).save()
- b2.authors.values() to show the authors of book 2
- a1.books.values() to show the books of author 1