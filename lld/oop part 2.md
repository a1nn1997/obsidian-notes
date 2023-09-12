# Constructor - 

^7e41af

1. constructors are methods that share the same name as the class and have no return type.
2. When a new object is created, one of the first things that happens is that the constructor is called
	1. c C = new C(); 
	2. The new keyword creates a new instance of the C class, thus allocating the required memory.
	3. Then the constructor itself is called, passing the arguments in the parameter list.
	4. The constructor provides the developer the opportunity to attend to the appropriate initialization.
 3. If the class provides no explicit constructor, a default constructor will be provided. 
 4. It is important to understand that at least one constructor always exists, regardless of whether you write a constructor yourself or not.
 5. Constructors are used to ensure that the application is in a stable state.
 6. Multiple objects can be instantiated from a single class. 
	 1. Each of these objects has a unique identity and state.
	 2. Each object is constructed separately and is allocated its own separate memory. 
	 3. If properly declared, be shared by all the objects instantiated from the same class, 
	 4. thus sharing the memory allocated for these class attributes and methods
# Overloading Method - 
 1. allows a programmer to use the same method name over and over, as long as the signature of the method is different each time.
 2. The signature consists of the method name and a parameter list 
		 eg public sum(int b, int c) {return (b+c) }   public sum (int a, int b, int c){ return (a+b+c)} together.
 3. Operator overloading allows you to change the meaning of an operator. eg c = "a"+ "b" here + act as concat not addn
# Super Class - 
1. The first thing that happens inside the constructor is that the constructor of the class’s superclass is called. 
	1. If there is no explicit call to the superclass constructor, 
	2. the default is called automatically; 
	3. however, you can see the code in the bytecodes. 
2. Then each class attribute of the object is initialized. 
	1. These are the attributes that are part of the class definition (instance variables), not the attributes inside the constructor or any other method (local variables). 
 3. Then the rest of the code in the constructor executes.
# Shallow Copy and Deep Copy
1. A deep copy is when all the references are followed and new copies are created for all referenced objects. 
	1. There might be many levels involved in a deep copy. 
	2. For objects with references to many objects, which in turn might have references to even more objects, the copy itself can create significant overhead. 
2. A shallow copy would simply copy the reference and not follow the levels. 


