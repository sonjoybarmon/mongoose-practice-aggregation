
# mongoose Practice Aggregation
## Example data:

```js
[
   /* 1 createdAt:05/06/2023, 00:00:16*/
{
	"_id" : ObjectId("647cd13032d4aff5457dc61a"),
	"name" : "Daniel Johnson",
	"email" : "danieljohnson@example.com",
	"age" : 33,
	"address" : {
		"street" : "890 Elm St",
		"city" : "Houston",
		"state" : "TX",
		"zipcode" : "77001"
	},
	"favorites" : {
		"color" : "green",
		"food" : "pizza",
		"movie" : "The Godfather"
	},
	"friends" : [
		{
			"name" : "Emily Wilson",
			"email" : "emilywilson@example.com"
		},
		{
			"name" : "Jacob Brown",
			"email" : "jacobbrown@example.com"
		}
	]
},

/* 2 createdAt:05/06/2023, 00:00:16*/
{
	"_id" : ObjectId("647cd13032d4aff5457dc619"),
	"name" : "Olivia Smith",
	"email" : "oliviasmith@example.com",
	"age" : 27,
	"address" : {
		"street" : "567 Pine St",
		"city" : "Phoenix",
		"state" : "AZ",
		"zipcode" : "85001"
	},
	"favorites" : {
		"color" : "purple",
		"food" : "sushi",
		"movie" : "The Notebook"
	},
	"friends" : [
		{
			"name" : "Sophia Davis",
			"email" : "sophiadavis@example.com"
		},
		{
			"name" : "James Wilson",
			"email" : "jameswilson@example.com"
		}
	]
},

/* 3 createdAt:05/06/2023, 00:00:16*/
{
	"_id" : ObjectId("647cd13032d4aff5457dc618"),
	"name" : "Henry Davis",
	"email" : "henrydavis@example.com",
	"age" : 45,
	"address" : {
		"street" : "123 Oak St",
		"city" : "Denver",
		"state" : "CO",
		"zipcode" : "80201"
	},
	"favorites" : {
		"color" : "blue",
		"food" : "steak",
		"movie" : "The Shawshank Redemption"
	},
	"friends" : [
		{
			"name" : "Lucy Thompson",
			"email" : "lucythompson@example.com"
		},
		{
			"name" : "William Johnson",
			"email" : "williamjohnson@example.com"
		}
	]
},

/* 4 createdAt:05/06/2023, 00:00:16*/
{
	"_id" : ObjectId("647cd13032d4aff5457dc617"),
	"name" : "Grace Taylor",
	"email" : "gracetaylor@example.com",
	"age" : 31,
	"address" : {
		"street" : "789 Cedar St",
		"city" : "Austin",
		"state" : "TX",
		"zipcode" : "78701"
	},
	"favorites" : {
		"color" : "teal",
		"food" : "tacos",
		"movie" : "The Avengers"
	},
	"friends" : [
		{
			"name" : "Ethan Wilson",
			"email" : "ethanwilson@example.com"
		},
		{
			"name" : "Sophie Anderson",
			"email" : "sophieanderson@example.com"
		}
	]
},

/* 5 createdAt:05/06/2023, 00:00:16*/
{
	"_id" : ObjectId("647cd13032d4aff5457dc616"),
	"name" : "Sophia Smith",
	"email" : "sophiasmith@example.com",
	"age" : 29,
	"address" : {
		"street" : "234 Cherry St",
		"city" : "Miami",
		"state" : "FL",
		"zipcode" : "33101"
	},
	"favorites" : {
		"color" : "orange",
		"food" : "sushi",
		"movie" : "Pulp Fiction"
	},
	"friends" : [
		{
			"name" : "Andrew Johnson",
			"email" : "andrewjohnson@example.com"
		},
		{
			"name" : "Oliver Brown",
			"email" : "oliverbrown@example.com"
		}
	]
},

/* 6 createdAt:05/06/2023, 00:00:16*/
{
	"_id" : ObjectId("647cd13032d4aff5457dc615"),
	"name" : "Michael Johnson",
	"email" : "michaeljohnson@example.com",
	"age" : 37,
	"address" : {
		"street" : "890 Maple St",
		"city" : "Dallas",
		"state" : "TX",
		"zipcode" : "75201"
	},
	"favorites" : {
		"color" : "yellow",
		"food" : "burger",
		"movie" : "The Matrix"
	},
	"friends" : [
		{
			"name" : "Jessica Wilson",
			"email" : "jessicawilson@example.com"
		},
		{
			"name" : "Daniel Davis",
			"email" : "danieldavis@example.com"
		}
	]
},

/* 7 createdAt:05/06/2023, 00:00:16*/
{
	"_id" : ObjectId("647cd13032d4aff5457dc614"),
	"name" : "Emma Wilson",
	"email" : "emmawilson@example.com",
	"age" : 24,
	"address" : {
		"street" : "567 Willow St",
		"city" : "Seattle",
		"state" : "WA",
		"zipcode" : "98101"
	},
	"favorites" : {
		"color" : "pink",
		"food" : "pasta",
		"movie" : "The Notebook"
	},
	"friends" : [
		{
			"name" : "Alex Thompson",
			"email" : "alexthompson@example.com"
		},
		{
			"name" : "Olivia Brown",
			"email" : "oliviabrown@example.com"
		}
	]
},

/* 8 createdAt:05/06/2023, 00:00:16*/
{
	"_id" : ObjectId("647cd13032d4aff5457dc613"),
	"name" : "David Brown",
	"email" : "davidbrown@example.com",
	"age" : 41,
	"address" : {
		"street" : "321 Pine St",
		"city" : "Chicago",
		"state" : "IL",
		"zipcode" : "60601"
	},
	"favorites" : {
		"color" : "red",
		"food" : "steak",
		"movie" : "The Dark Knight"
	},
	"friends" : [
		{
			"name" : "Karen Miller",
			"email" : "karenmiller@example.com"
		},
		{
			"name" : "Michael Davis",
			"email" : "michaeldavis@example.com"
		}
	]
},

/* 9 createdAt:05/06/2023, 00:00:16*/
{
	"_id" : ObjectId("647cd13032d4aff5457dc612"),
	"name" : "Sarah Johnson",
	"email" : "sarahjohnson@example.com",
	"age" : 32,
	"address" : {
		"street" : "789 Oak St",
		"city" : "Los Angeles",
		"state" : "CA",
		"zipcode" : "90001"
	},
	"favorites" : {
		"color" : "purple",
		"food" : "tacos",
		"movie" : "Inception"
	},
	"friends" : [
		{
			"name" : "Mark Smith",
			"email" : "marksmith@example.com"
		},
		{
			"name" : "Amy Wilson",
			"email" : "amywilson@example.com"
		}
	]
},

/* 10 createdAt:05/06/2023, 00:00:16*/
{
	"_id" : ObjectId("647cd13032d4aff5457dc611"),
	"name" : "Alice Williams",
	"email" : "alicewilliams@example.com",
	"age" : 35,
	"address" : {
		"street" : "456 Elm St",
		"city" : "San Francisco",
		"state" : "CA",
		"zipcode" : "94101"
	},
	"favorites" : {
		"color" : "green",
		"food" : "sushi",
		"movie" : "The Godfather"
	},
	"friends" : [
		{
			"name" : "Bob Anderson",
			"email" : "bobanderson@example.com"
		},
		{
			"name" : "Emily Davis",
			"email" : "emilydavis@example.com"
		}
	]
},

/* 11 createdAt:05/06/2023, 00:00:16*/
{
	"_id" : ObjectId("647cd13032d4aff5457dc610"),
	"name" : "John Doe",
	"email" : "johndoe@example.com",
	"age" : 28,
	"address" : {
		"street" : "123 Main St",
		"city" : "New York",
		"state" : "NY",
		"zipcode" : "10001"
	},
	"favorites" : {
		"color" : "blue",
		"food" : "pizza",
		"movie" : "The Shawshank Redemption"
	},
	"friends" : [
		{
			"name" : "Jane Smith",
			"email" : "janesmith@example.com"
		},
		{
			"name" : "Mike Johnson",
			"email" : "mikejohnson@example.com"
		}
	]
}
 ]
```

**Task 1:** Find all users who are located in New York.

**Task 2:** Find the user(s) with the email "**[johndoe@example.com](mailto:johndoe@example.com)**" and retrieve their favorite movie.

**Task 3:** Find all users with "pizza" as their favorite food and sort them according to age.

**Task 4**: Find all users over 30 whose favorite color is "green".

**Task 5:** Count the number of users whose favorite movie is "The Shawshank Redemption."

**Task 6:** Update the zipcode of the user with the email "**[johndoe@example.com](mailto:johndoe@example.com)**" to "10002".

**Task 7:** Delete the user with the email "**[alicewilliams@example.com](mailto:alicewilliams@example.com)**" from the user data.

**Task 8**: Group users by their favorite movie and retrieve the average age in each movie group.

**Task 9:** Calculate the average age of users with a favorite " pizza " food.

```js
// orders
[
  {
    "_id": 1,
    "order_number": "ORD-001",
    "customer_id": 1,
    "total_amount": 100.0
  },
  {
    "_id": 2,
    "order_number": "ORD-002",
    "customer_id": 2,
    "total_amount": 150.0
  },
  {
    "_id": 3,
    "order_number": "ORD-003",
    "customer_id": 1,
    "total_amount": 200.0
  }
]

// customers
[
  {
    "_id": 1,
    "name": "Alice Williams",
    "email": "alice@example.com"
  },
  {
    "_id": 2,
    "name": "Bob Anderson",
    "email": "bob@example.com"
  },
  {
    "_id": 3,
    "name": "Emily Davis",
    "email": "emily@example.com"
  }
]
```

**Task 10:** Perform a lookup aggregation to retrieve the orders data along with the customer details for each order.

## More Tasks on Aggregation

**Task 1:** Group users by their favorite color and retrieve the count of users in each color group.

**Task 2:** Find the user(s) with the highest age.

**Task 3:** Find the most common favorite food among all users.

**Task 4:** Calculate the total count of friends across all users.

**Task 5:** Find the user(s) with the longest name.

**Task 6:** Calculate each state's total number of users in the address field.

**Task 7:** Find the user(s) with the highest number of friends.

These tasks involve using various aggregation operators such as **`$group`**, **`$avg`**, **`$max`**, **`$sum`**, and **`$project`** to perform complex calculations and data transformations. You can write MongoDB aggregation queries to accomplish each task based on user data. Adjust the queries according to your specific implementation and requirements.
