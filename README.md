# ASP.NET Core and MongoDB Web API [Demo]

**Basic CURD Web API with MongoDB and ASP.NET demonstration.**

## MongoDB Configuration
In order to run this demo, first we need to configure the database and add some entries.

 - Inside the mongo shell, create a database named *BookstoreDb*
 
    **```use BookstoreDb```**
    
 - Create a new Books Collection

	 **```db.createCollection('Books')```**

 - Define a schema for the *Books Collection* and insert two documents
 
	 **```db.Books.insertMany([{'Name':'Design Patterns','Price':54.93,'Category':'Computers','Author':'Ralph Johnson'}, {'Name':'Clean Code','Price':43.15,'Category':'Computers','Author':'Robert C. Martin'}])```**

 - Show the documents inserted in the previous step
 
	 **```db.Books.find({}).pretty()```**

	*Should we have something like this*
```
{
	"_id": ObjectId("5bfd996f7b8e48dc15ff215d"),
	"Name": "Design Patterns",
	"Price": 54.93,
	"Category": "Computers",
	"Author": "Ralph Johnson"
} {
	"_id": ObjectId("5bfd996f7b8e48dc15ff215e"),
	"Name": "Clean Code",
	"Price": 43.15,
	"Category": "Computers",
	"Author": "Robert C. Martin"
}
```


## Testing the Web API

 - Show all entries 
	**```[GET] http://localhost:5001/api/books```**
	
 - Get by ID
	 **```[GET] http://localhost:5001/api/books/<id>```**
