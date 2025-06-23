### HashMap

It provides the basic implementation of the Map interface in Java.HashMap stores data in (key, value) pairs.

- Not synchronized (unlike Hashtable in Java) and hence faster for most of the cases.
- Only one null key object, and there can be any number of null values.
- Duplicate keys are not allowed in HashMap
- HashMap allows for efficient key-based retrieval, insertion, and removal with an average O(1) time complexity.

```note
    HashMap<String, Integer> hashMap = new HashMap<>();

      hashMap.put("John", 25);
      hashMap.put("Jane", 30);
      hashMap.put("Jim", 35);

      System.out.println(hashMap.get("John")); // Output: 25

      hashMap.remove("Jim");

      System.out.println(hashMap.containsKey("Jim")); // Output:false

      System.out.println(hashMap.size()); // Output: 2

```

**Keys and value can't be primitive datatype**

**Key in Hashmap is valid if it implements hashCode() and equals() method**

**Value in hashmap can be any wrapper class, custom objects, arrays, any reference type or even null . For example, Hashmap can have array as value but not as key.**

### Characteristics of HashMap

- `Not ordered` : the order in which elements are added to the map is not preserved

- `Thread-unsafe`: If thread safety is required, ConcurrentHashMap can be used.

- `Capacity` : which is the number of elements that it can hold
- `load factor`: which is the measure of how full the hashmap can be before it is resized.

### 4 types of HashMap Constructors

### 1. HashMap():

It is the default constructor which creates an instance of HashMap with an initial capacity of 16 and a load factor of 0.75.

```note
HashMap<Integer, String> hm1 = new HashMap<>();
```

### 2. HashMap(int initialCapacity)

It creates a HashMap instance with a specified initial capacity and load factor of 0.75.

```note
HashMap<Integer, String> hm1 = new HashMap<>(10);
```

### 3. HashMap(int initialCapacity, float loadFactor)

It creates a HashMap instance with a specified initial capacity and specified load factor.

```note
HashMap<Integer, String> hm1 = new HashMap<>(5, 0.75f);
```

### 4. HashMap(Map map)

It creates an instance of HashMap with the same mappings as the specified map.

```note
Map<Integer, String> hm1 = new HashMap<>();
hm1.put(1, "one");
hm1.put(2, "two");
hm1.put(3, "three");

HashMap<Integer, String> hm2 = new HashMap<Integer, String>(hm1);
```

### Performing Various Operations on HashMap

### 1. Adding Elements in HashMap in Java:

hm1.put(1, "Geeks");

### 2.Removing Element from Java HashMap

hm.remove(4);

### 3.Traversal of Java HashMap

```note
for (Map.Entry<String, Integer> e : map.entrySet()) {
 System.out.println("Key: " + e.getKey()+ " Value: " + e.getValue());
}

```
