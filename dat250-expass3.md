# DAT250: Software Technology Experiment Assignment 3  

## Experiment 1: MongoDB CRUD operations

### Results from insert operation  
Here I have shown a successfull insert many operation:
![image](https://github.com/Mamo-00/dat250assignment1/assets/60385659/00103837-09d7-45bc-be8a-de5f940afa54)

### Results from query operation  
These are the results from querying using AND - OR operations  
![image](https://github.com/Mamo-00/dat250assignment1/assets/60385659/5547367b-d784-4b7a-bcb7-dc5dffac6a29)

### Results from update operation  
Here are the results from an update many operation  
![image](https://github.com/Mamo-00/dat250assignment1/assets/60385659/372ef231-7f4e-4aea-971a-e8760e49b000)

### Results from remove operation  
Here the first document that has status D is removed  
![image](https://github.com/Mamo-00/dat250assignment1/assets/60385659/2761bbb8-a704-4a7a-9ee2-d1bcdf114e56)

### Results from bulk-write operations  
This is the result from a bulk-write operation using insertOne, updateOne, deleteOne, and replaceOne operations
![image](https://github.com/Mamo-00/dat250assignment1/assets/60385659/f7be191a-d19a-403d-8fd4-5cf44262fd1b)

## Experiment 2: Aggregation  

### Experiment 2 example part
This is the result from experiment 2 map-reduce example  
![image](https://github.com/Mamo-00/dat250assignment1/assets/60385659/4e75081b-9c44-40c8-862a-6325429b7f12)

### Experiment 2 custom function part

Map function:  
emit the sku field as the key using a loop and map the total price and quantity to it.
![image](https://github.com/Mamo-00/dat250assignment1/assets/60385659/b88fd1a9-0be6-4527-a12a-77b42179cc8e)  

Reduce function:  
in this reduce function you sum up the total price, total quantity and total count of all SKUs of a specific kind  
such as the total price of all apple orders, total quantity of all apple orders and the number of apple orders
  
Note: When I was adding new lines it gave me a couple unexpected token errors so I just did it in on a single line
![image](https://github.com/Mamo-00/dat250assignment1/assets/60385659/7dd8a821-e9a8-42e3-b856-98e46eb44f15)

Finalize function:  
Here you will calculate the average price and the average quantity
![image](https://github.com/Mamo-00/dat250assignment1/assets/60385659/bef968ec-4926-4e02-a646-24fd4b606dbb)

MapReduce operation:  
And here we run the MapReduce function which will write the output to a new collection named "map_reduce_sku_analysis"
![image](https://github.com/Mamo-00/dat250assignment1/assets/60385659/386a7ce8-798e-49e9-b96b-21efaf13032d)

Displaying results:  
These are the results of the average price and quantity of each SKU
![image](https://github.com/Mamo-00/dat250assignment1/assets/60385659/41e9323d-279e-4295-9a20-d889a4930d2e)

### Purpose of my custom map-reduce operation

This map-reduce operation is useful because it helps you in inventory planning and management by knowing the total   
quantity and price average and you can make a price strategy based on the averages you get.  
The collection you get when you run the map-reduce operation has an id field that represents the item and a value field  
that is an object containing information about the item such as:  
- the total price of all orders of that item,
- the total quantity of that item across all orders (if we take apples as an example, then this would mean how many apples were ordered)
- how many orders of that item (this would mean how many apple orders)
- the average price and average quantity

### Problems that I encountered
The biggest problem that I encountered is running the map-reduce function in mongosh in the MongoDB Compass, which is why you will notice the   
screenshots look different because some of them are from the mongo shell in compass and the map reduce ones are from the command line














