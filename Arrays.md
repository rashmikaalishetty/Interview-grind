### Arrays

Allow us to store multiple values of the same type in a single variable.

Arrays in Java are objects

`Primitive arrays` elements are stored in a contiguous memory.

`Non-Primitive arrays:` references are stored at contiguous locations, but the actual objects may be at different locations in memory.

**Key features of Arrays:**

- Contiguous Memory Allocation (for Primitives)
- Zero-based Indexing
- Fixed Length
- Can Store Primitives & Objects: Java arrays can hold both primitive types (like int, char, boolean, etc.) and objects (like String, Integer, etc.)

`Heap`: The heap is a part of memory in Java where objects are stored at runtime

```note
int[] arr = new int[5];

arr is a reference variable (stored in the stack).
The actual array object (with 5 integers) is stored in the heap.
```

**You can imagine the stack holding "pointers" or "addresses" to heap-allocated objects.**

class-level array reference stored in the `heap`

To use new to allocate an array, you must specify the type and number of elements to allocate.

int[] intArray = new int[20];

### Types of Arrays:

`1.Single-Dimensional Arrays`: elements are stored in a linear order

```note
int[] singleDimArray = {1, 2, 3, 4, 5};
```

`2.Multi-Dimensional Arrays`: Arrays with more than one dimension, such as two-dimensional arrays (matrices).

```note
int[][] multiDimArray = {
      {1, 2, 3},
     {4, 5, 6},
     {7, 8, 9} };
```

### For-Each Loop

they are also called enhanced for loop , used when the exact index of an element is not required.

**Limitations of for each loop**

- Cannot Modify Array Elements Directly

```note
for (int num : marks)  {
num = num*2;
}

The for-each loop gives a copy of each element for `primitives` and the copy of the reference for `objects`.

Changing num just changes the local loop variable.The original marks array stays unchanged.
```

for objects

```note
Person[] people = { new Person("Rashmika") };
for (Person p : people) {
    p.name = "Rahul";      // ✅ This modifies the actual object
    p = new Person("New");    // ❌ This does NOT change the array
}

p is a copy of the reference — it points to the actual object in memory.
p.name = ... changes the field inside the actual object → visible outside the loop.
But doing p = new Person(...) just reassigns the local variable p to point elsewhere — it does not update the people array.
```

- No access to index.

- Single Iteration only.

**While finding min or max value in the array, always initialize max variable to the first element bcoz it works for all data types - positive, negative, zero.
While in ArrayList its better to use Interger.MIN_VALUE , its safe when list is empty(otherwise list.get(0) would throw null pointer exception)**

### Array Members

Arrays are objects of a class, and a direct superclass of arrays is a class `Object.

All the members are inherited from class Object, the only method of Object that is not inherited is its `clone` method.

#### Clone method

used to clone an object. It creates a new instance of the class of the current object and initializes all its fields with exactly the contents of the corresponding fields of this object.

`Shallow cloning` : Only the top-level object is duplicated.If the original object has references to other objects, the clone still shares those references (not independent).

p1.address and p2.address point to the same Address object.

`Deep Cloning`: The object and all nested objects are cloned.Fully independent copy.

p2.address is a different object.Changing it won’t affect p1.address

### Advantages of Java Arrays

- Efficient Access: Accessing an element by its index is fast and has constant time complexity, O(1).

- Memory Management: Arrays have fixed size, which makes memory management straightforward and predictable.

- Data Organization: Arrays help organize data in a structured manner, making it easier to manage related elements.

### Disadvantages of Java Arrays

- Fixed Size: Once an array is created, its size cannot be changed, which can lead to memory waste if the size is overestimated or insufficient storage if underestimated.

- Type Homogeneity

- Insertion and Deletion: Inserting or deleting elements, especially in the middle of an array, can be costly as it may require shifting elements.
