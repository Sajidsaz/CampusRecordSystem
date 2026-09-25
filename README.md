# University Student Record and Campus Route Management System

**Module:** CIT300 – Data Structures and Algorithms  
**Assignment:** Graded Practical Assignment 1 (Week 10)  
**University:** SLTC Research University  

---

## 1. Project Overview

The **University Student Record and Campus Route Management System** is a Java console application developed to demonstrate the practical use of core data structures and algorithms.

The system manages university student records and models campus locations as a connected network of roads. It combines six main data structures:

- Linked List
- Stack
- Queue
- Binary Search Tree (BST)
- Hash Table
- Graph

The application provides a menu-driven interface that allows users to manage student records, process service requests, view recent actions, search and display students using different data structures, and manage campus locations and routes.

---

## 2. Team Members

| Member | Name | Student ID | Responsibility | Individual Contribution |
|---|---|---|---|---|
| Member 1 | MRM. Ilham | 23DA2-1000 | Student Model and Linked List | Implemented the `Student` model and `LinkedListManager`, including student insertion, duplicate-ID checking, searching, updating, deleting, and displaying all student records. |
| Member 2 | MF. Hasan | 23DA2-1001 | Stack and Queue | Implemented `ActionStack` for recent-action history and `ServiceQueue` for FIFO service-request processing, including push, pop, display, enqueue, dequeue, and empty-state handling. |
| Member 3 | AM. Naashir | 23DA2-0650 | BST and Hash Table | Implemented `BSTManager` for ordered student storage/display and `HashTableManager` for fast student-ID lookup with separate chaining for collisions. |
| Member 4 | S. Sajidh Ahamed | 23DA2-0840 | Graph, Main Integration and Documentation | Implemented `CampusGraph`, campus location/road management, BFS and DFS traversal, integrated all modules through `Main.java`, added input validation, and maintained project documentation. |

---

## 3. Data Structures Used

| Structure | Purpose in the System | File | Main Operations / Menu Options |
|---|---|---|---|
| Linked List | Main storage and management of student records | `src/records/LinkedListManager.java` | Add, search, update, delete, display — Options 1–4 |
| Stack | Stores recent system actions using LIFO order | `src/records/ActionStack.java` | Push actions, display action history — Option 7 |
| Queue | Processes service requests in FIFO order | `src/records/ServiceQueue.java` | Enqueue and dequeue requests — Options 5–6 |
| Binary Search Tree | Stores students ordered by Student ID and displays them using in-order traversal | `src/search/BSTManager.java` | Insert and display sorted records — Option 8 |
| Hash Table | Provides fast student lookup by Student ID using separate chaining | `src/search/HashTableManager.java` | Insert and search — Option 9 |
| Graph | Represents campus locations and roads using an adjacency list | `src/graph/CampusGraph.java` | Location/road management, display, BFS, DFS — Options 10–15 |

### Student Model

Student information is represented by:

`src/model/Student.java`

Each student contains:

- Student ID
- Name
- Programme
- Marks

A `Student` object is inserted into the linked list and is also referenced by the BST and hash table when a new student is added through the main application.

---

## 4. Main Menu

```text
==================================================
 UNIVERSITY STUDENT RECORD & CAMPUS ROUTE SYSTEM
==================================================

1.  Add Student Record
2.  Update Student Record
3.  Delete Student Record
4.  Display All Records using Linked List
5.  Add Service Request to Queue
6.  Process Next Service Request
7.  Display Recent Actions using Stack
8.  Display Students using BST
9.  Search Student using Hashing
10. Add Campus Location
11. Remove Campus Location
12. Add Campus Connection/Road
13. Remove Campus Connection/Road
14. Display Campus Connections
15. Traverse Campus Locations using BFS or DFS
16. Exit
```

---

## 5. Features Implemented

- [x] Student records with ID, Name, Programme, and Marks
- [x] Student model with constructor, getters, setters, and formatted output
- [x] Custom singly linked list implementation
- [x] Add student record
- [x] Prevent duplicate student IDs in the linked list
- [x] Search student by ID
- [x] Update student record
- [x] Delete student record
- [x] Display all student records
- [x] Stack-based recent action history
- [x] Queue-based service request processing
- [x] Binary Search Tree insertion
- [x] BST in-order traversal for ordered student display
- [x] Hash-table student lookup
- [x] Separate chaining for hash collisions
- [x] Campus graph using an adjacency list
- [x] Add campus locations
- [x] Remove campus locations
- [x] Add campus roads/connections
- [x] Remove campus roads/connections
- [x] Display campus connections
- [x] Breadth-First Search (BFS) traversal
- [x] Depth-First Search (DFS) traversal
- [x] Menu-driven console interface
- [x] Integer input validation
- [x] Marks validation between 0 and 100
- [x] Error handling for duplicate locations and missing records/connections

---

## 6. Project Structure

```text
CampusRecordSystem/
├── bin/
├── lib/
├── src/
│   ├── app/
│   │   └── Main.java
│   ├── graph/
│   │   └── CampusGraph.java
│   ├── model/
│   │   └── Student.java
│   ├── records/
│   │   ├── LinkedListManager.java
│   │   ├── ActionStack.java
│   │   └── ServiceQueue.java
│   └── search/
│       ├── BSTManager.java
│       └── HashTableManager.java
├── .gitignore
└── README.md
```

> `bin/` contains compiled `.class` files when the project is compiled locally. Compiled files should normally be excluded from Git using `.gitignore`.

---

## 7. How to Compile and Run

### Option 1 — Compile from the Project Root

Open Command Prompt or Terminal inside the `CampusRecordSystem` folder.

Create the `bin` folder if it does not already exist:

```bash
mkdir bin
```

Compile all Java source files:

```bash
javac -d bin src\model\Student.java src\records\LinkedListManager.java src\records\ActionStack.java src\records\ServiceQueue.java src\search\BSTManager.java src\search\HashTableManager.java src\graph\CampusGraph.java src\app\Main.java
```

Run the application:

```bash
java -cp bin app.Main
```

### Option 2 — Compile from the `src` Folder

```bash
cd src
javac -d ../bin model/*.java records/*.java search/*.java graph/*.java app/*.java
java -cp ../bin app.Main
```

### Option 3 — Run with VS Code

1. Open the `CampusRecordSystem` folder in VS Code.
2. Open `src/app/Main.java`.
3. Make sure the Java Extension Pack is installed.
4. Click **Run** above the `main()` method.

---

## 8. Data Structure Details

### 8.1 Linked List

`LinkedListManager` implements a custom singly linked list.

Each node stores:

- A `Student` object
- A reference to the next node

Main operations:

- `addStudent()`
- `search()`
- `updateStudent()`
- `deleteStudent()`
- `displayAll()`

Example:

```text
HEAD
 |
 v
[Student 1 | next] -> [Student 2 | next] -> [Student 3 | null]
```

### 8.2 Stack

`ActionStack` stores recent actions using the **LIFO** principle: **Last In, First Out**.

Main operations:

- `push()`
- `pop()`
- `displayHistory()`

### 8.3 Queue

`ServiceQueue` processes service requests using the **FIFO** principle: **First In, First Out**.

Main operations:

- `enqueue()`
- `dequeue()`
- `isEmpty()`

### 8.4 Binary Search Tree

`BSTManager` stores students according to Student ID.

- Smaller IDs go to the left subtree.
- Larger IDs go to the right subtree.
- In-order traversal displays records in Student ID order.

Main operations:

- `insert()`
- `displayInOrder()`

### 8.5 Hash Table

`HashTableManager` provides fast student lookup by Student ID.

The hash function converts the student ID into a table index. If two student IDs produce the same index, the implementation handles the collision using **separate chaining**.

Main operations:

- `insert()`
- `search()`

### 8.6 Graph

`CampusGraph` represents the university campus as an undirected graph.

- Vertices represent campus locations.
- Edges represent roads/connections.
- An adjacency list stores the graph.

Main operations:

- `addLocation()`
- `removeLocation()`
- `addConnection()`
- `removeConnection()`
- `displayGraph()`
- `bfsTraversal()`
- `dfsTraversal()`

---

## 9. BFS and DFS Traversal

### Breadth-First Search (BFS)

BFS visits neighboring locations level by level. The implementation uses a queue and a set of visited locations.

### Depth-First Search (DFS)

DFS follows a path as deeply as possible before backtracking. The implementation uses recursion and a set of visited locations.

Both traversal methods prevent already visited locations from being processed repeatedly.

---

## 10. Input Validation

The application includes validation for common input problems, including:

- Invalid integer menu input
- Invalid marks input
- Marks outside the range `0–100`
- Duplicate Student IDs in the linked-list record store
- Student record not found
- Duplicate campus locations
- Missing campus locations
- Duplicate roads/connections
- Missing roads/connections
- Invalid BFS/DFS selection
- Empty service-request queue

---

## 11. Collaboration and GitHub Workflow

The project was developed collaboratively using Git and GitHub.

Each team member worked on a separate feature branch:

```text
main
├── member1-student-linkedlist
├── member2-stack-queue
├── member3-bst-hashtable
└── member4-graph-integration
```

### Member Responsibilities

**Member 1**

```text
src/model/Student.java
src/records/LinkedListManager.java
```

**Member 2**

```text
src/records/ActionStack.java
src/records/ServiceQueue.java
```

**Member 3**

```text
src/search/BSTManager.java
src/search/HashTableManager.java
```

**Member 4**

```text
src/graph/CampusGraph.java
src/app/Main.java
README.md
```

Branches were pushed to GitHub and merged into `main` after integration and review.

The repository commit and Pull Request history provides evidence of individual contributions.

---

## 12. Testing

The system should be tested using the following workflow:

1. Add multiple student records.
2. Attempt to add a duplicate Student ID.
3. Display all students.
4. Update an existing student.
5. Attempt to update a missing student.
6. Delete a student.
7. Add multiple service requests.
8. Process service requests and verify FIFO order.
9. Display recent actions and verify stack order.
10. Display students using the BST.
11. Search for an existing student using the hash table.
12. Search for a non-existing student.
13. Add campus locations.
14. Add campus connections.
15. Display the campus graph.
16. Run BFS from an existing location.
17. Run DFS from an existing location.
18. Remove a connection.
19. Remove a location.
20. Test invalid numeric input and marks outside `0–100`.

---

## 13. Known Design Limitation

The current implementation inserts newly created `Student` objects into the linked list, BST, and hash table.

Because these structures reference the same `Student` object, changes to the student's fields can be visible through those references.

However, deletion currently removes the student record from the linked list only. The current `BSTManager` and `HashTableManager` implementations do not include structural delete operations.

Therefore, after deleting a student through the linked-list menu option, that student's previous entry may still remain structurally present in the BST or hash table.

This limitation should be considered during testing and future improvements.

---

## 14. Future Improvements

Possible improvements include:

- Add BST delete functionality
- Add hash-table delete functionality
- Keep all student data structures fully synchronized after deletion
- Add direct BST student search
- Add persistent file/database storage
- Add shortest-path campus routing
- Add weighted roads/distances
- Add graphical user interface
- Add automated unit tests
- Improve reporting and student statistics

---

## 15. Demonstration Video

**Video Link:**  
`[Add the merged group demonstration video link here]`

Each member should explain and demonstrate the part they personally implemented.

Suggested order:

1. **Member 1** — Student model and Linked List
2. **Member 2** — Stack and Queue
3. **Member 3** — BST and Hash Table
4. **Member 4** — Campus Graph, BFS/DFS, Main integration and final system demonstration

---

## 16. Conclusion

The University Student Record and Campus Route Management System demonstrates how multiple data structures can be combined within one Java application.

The project applies linked lists, stacks, queues, binary search trees, hash tables, and graphs to practical university-related tasks while also demonstrating searching, traversal, data management, input validation, modular programming, and collaborative development using Git and GitHub.
