# Java for Python Programmers: Competitive Programming & DSA Sprint

An intensive, streamlined survival guide and 18-problem roadmap to transition your Python DSA knowledge into Java for competitive programming.

---

## 🗺️ The 18-Problem HackerRank Roadmap

### I/O & Types 
* [Java Stdin and Stdout II](https://www.hackerrank.com/challenges/java-stdin-stdout/problem)
* [Java Datatypes](https://www.hackerrank.com/challenges/java-datatypes/problem)
* [Java End-of-file](https://www.hackerrank.com/challenges/java-end-of-file/problem)

### Strings 
* [Java Strings Introduction](https://www.hackerrank.com/challenges/java-strings-introduction/problem)
* [Java Substring Comparisons](https://www.hackerrank.com/challenges/java-string-comparisons/problem)
* [Java String Reverse](https://www.hackerrank.com/challenges/java-string-reverse/problem)
* [Java Anagrams](https://www.hackerrank.com/challenges/java-anagrams/problem)
* [Java String Tokens](https://www.hackerrank.com/challenges/java-string-tokens/problem)

### Data Structures - JCF 
* [Java 2D Array](https://www.hackerrank.com/challenges/java-2d-array/problem)
* [Java Arraylist](https://www.hackerrank.com/challenges/java-arraylist/problem)
* [Java List](https://www.hackerrank.com/challenges/java-list/problem)
* [Java Map](https://www.hackerrank.com/challenges/java-map/problem)
* [Java Hashset](https://www.hackerrank.com/challenges/java-hashset/problem)
* [Java Stack](https://www.hackerrank.com/challenges/java-stack/problem)
* [Java Priority Queue](https://www.hackerrank.com/challenges/java-priority-queue/problem)
* [Java Dequeue](https://www.hackerrank.com/challenges/java-dequeue/problem)

### Custom Sorting 
* [Java Comparator](https://www.hackerrank.com/challenges/java-comparator/problem)
* [Java Sort](https://www.hackerrank.com/challenges/java-sort/problem)

---

## ⚡ Complete Python-to-Java Syntax & Methods Cheat Sheet

### 1. Basic Structure & Boilerplate
Every standalone Java program needs a class and a main method:
```java
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        // Your code here
        sc.close();
    }
}
```

### 2. Strings & Characters
Strings in Java are **immutable**. Always use `StringBuilder` for heavy modifications inside loops to prevent Time Limit Exceeded (TLE) errors.

| Operation | Python | Java Equivalent |
| :--- | :--- | :--- |
| **Length** | `len(s)` | `s.length()` |
| **Get Char** | `s[i]` | `s.charAt(i)` |
| **Substring** | `s[start:end]` | `s.substring(start, end)` |
| **Split** | `s.split(",")` | `s.split(",")` |
| **String to Array**| `list(s)` | `s.toCharArray()` |
| **Array to String**| `"".join(arr)` | `new String(arr)` |
| **Mutable String**| `list(s)` | `StringBuilder sb = new StringBuilder(s);` |
| **Append Char** | `s += 'a'` | `sb.append('a');` |
| **Reverse** | `s[::-1]` | `sb.reverse().toString();` |
| **Is Digit** | `char.isdigit()` | `Character.isDigit(ch)` |

### 3. Arrays vs. ArrayLists
* **Primitive Arrays (`int[]`)**: Fixed size, fast, primitive memory footprint.
* **ArrayList (`ArrayList<Integer>`)**: Dynamic size, stores object wrappers (`Integer`, not `int`).

| Operation | Java Array (`int[]`) | Java ArrayList (`ArrayList<Integer>`) |
| :--- | :--- | :--- |
| **Initialization** | `int[] arr = new int[10];` | `ArrayList<Integer> list = new ArrayList<>();` |
| **Size / Length** | `arr.length` *(no parentheses)* | `list.size()` |
| **Access Item** | `arr[i]` | `list.get(i)` |
| **Update Item** | `arr[i] = 5;` | `list.set(i, 5);` |
| **Add Item** | *Fixed size* | `list.add(5);` |
| **Sorting** | `Arrays.sort(arr);` | `Collections.sort(list);` |
| **Filling** | `Arrays.fill(arr, 0);` | N/A |

### 4. HashMaps & HashSets (JCF)

| Operation | Java HashMap | Java HashSet |
| :--- | :--- | :--- |
| **Initialization** | `Map<String, Integer> map = new HashMap<>();` | `Set<Integer> set = new HashSet<>();` |
| **Insert / Put** | `map.put("key", 1);` | `set.add(5);` |
| **Lookup / Check** | `map.containsKey("key")` | `set.contains(5);` |
| **Get w/ Default** | `map.getOrDefault("key", 0);` | N/A |
| **Iteration** | `for (Map.Entry<String, Integer> e : map.entrySet()) { ... }` | `for (int x : set) { ... }` |

### 5. Stacks, Queues, and Heaps

| Structure | Java Class Initialization | Key Methods |
| :--- | :--- | :--- |
| **Stack** | `Stack<Integer> s = new Stack<>();` | `s.push(x)`, `s.pop()`, `s.peek()`, `s.isEmpty()` |
| **Queue (BFS)** | `Queue<Integer> q = new LinkedList<>();` | `q.offer(x)`, `q.poll()`, `q.peek()`, `q.isEmpty()` |
| **Deque** | `Deque<Integer> dq = new ArrayDeque<>();` | `dq.offerFirst()`, `dq.pollLast()`, etc. |
| **Min-Heap** | `PriorityQueue<Integer> pq = new PriorityQueue<>();` | `pq.offer(x)`, `pq.poll()`, `pq.peek()` |
| **Max-Heap** | `PriorityQueue<Integer> pq = new PriorityQueue<>(Collections.reverseOrder());` | `pq.offer(x)`, `pq.poll()` |

### 6. Math & Boundary Constants
Java does not have a `**` operator or `float('inf')`. Use these alternatives:
* **Powers:** `Math.pow(2, n)` (returns `double`) or bitwise shift `1L << n` (fast for integers).
* **Max/Min Values:**
  * `Integer.MAX_VALUE` / `Integer.MIN_VALUE`
  * `Long.MAX_VALUE` / `Long.MIN_VALUE`
  * `Byte.MAX_VALUE` / `Byte.MIN_VALUE`
  * `Short.MAX_VALUE` / `Short.MIN_VALUE`
* **Absolute / Max:** `Math.abs(x)`, `Math.max(a, b)`, `Math.min(a, b)`

---

## 🚨 Pro-Tips & Competitive Programming Gotchas

1. **The Scanner Newline Bug:** 
   When using `Scanner`, calling `sc.nextInt()` or `sc.nextDouble()` leaves a trailing newline character (`\n`) in the buffer. If you call `sc.nextLine()` right after, it reads that blank line. **Fix:** Add a dummy `sc.nextLine();` right after reading a number.
2. **Primitive vs. Wrapper Classes:** 
   Java collections (`ArrayList`, `HashMap`, `PriorityQueue`) cannot hold primitive types like `int` or `char`. You must use their object wrapper counterparts: `Integer`, `Character`, `Long`, `Double`, `Boolean`.
3. **Data Type Constraints & Try-Catch:**
   When checking whether a number fits in `byte`, `short`, `int`, or `long`, use bounds (`Byte.MIN_VALUE` to `Byte.MAX_VALUE`). If an input exceeds 64-bit limits, `sc.nextLong()` throws an exception. Wrap input parsing in a `try-catch` block to handle numbers that "can't be fitted anywhere."
4. **Custom Comparators via Lambdas:**
   To sort 2D arrays or custom objects in Java:
   ```java
   Arrays.sort(intervals, (a, b) -> Integer.compare(a[0], b[0]));
   ```
