# thing everything in terms of objects
1.  there is no single right or wrong way to approach a problem. There are usually many different ways to tackle the same problem. (there will always be room for improvement). 
2. The first order of business is to identify and solve business problems. 
	1. Work on the conceptual analysis and design first. 
	2. Only think about specific technologies when they are fundamental to the business problem.
3. when you write an OO application, you are using structured constructs everywhere. 
	1. When moving to an OO language, you must go through the investment of learning OO concepts and the corresponding thought process first.
4. Three important things you can do to develop a good sense of the OO thought process  
	1. Knowing the difference between the interface and implementation 
		1. [[programmer]] must understand classes and how to use them.  [[end-user]] only focus on gui and end usage.
		2. Properly constructed classes are designed in two parts—the interface and the implementation.
			1. The services presented to an end user comprise the interface.
			2. The implementation details are hidden from the user. 
				1. Implementation should not require a change to the user’s code.
			3. Remember that the interface includes the syntax to call a method and return a value. 
				1. If this interface does not change, the user does not care whether the implementation is changed.
			4. Minimal Interface only give class feature when user need it.
		3. ( oo class ) -> ( rds ) using middleware product (eg sql archamy) 
			1. OO databases are much more efficient for object persistence than relational databases. 
			2. Object persistence refers to the concept of saving the state of an object so that it can be restored and used at a later time. 
			3. An object that does not persist basically dies when it goes out of scope. For example, the state of an object can be saved in a database
			4. the current business environment, relational-to-object mapping is a great solution. eg sqlarchamy. 
			5. Standalone Application Even when creating a new OO application from scratch, it might not be easy to avoid legacy data. 
			6. This is due to the fact that even a newly created OO application is most likely not a standalone application and might need to exchange information stored in relational database.
	2. Thinking more abstractly.
		1. One of the main advantages of OO programming is that classes can be reused. 
			1. Concrete interfaces tend to be very specific, 
			2. whereas abstract interfaces are more general
	3. Giving the user the minimal interface possible.
		1.  When designing a class, the rule of thumb is to always provide the user with as little knowledge of the inner workings of the class as possible.
			1. Give the users only what they absolutely need.
			2. It is vital to design classes from a user’s perspective and not from an information systems viewpoint.
			3. design of the class to make it fit into a specific technological model.
			4. Make sure when you are designing a class that you go over the requirements.
			5. the design with the people who will actually use it—not just developers.

 # OOP Part 2
 [[oop part 2]]
