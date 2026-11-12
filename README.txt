TEAM NEXUS - UPDATED C++ CONSOLE PROJECT
========================================

FILES TO KEEP TOGETHER
----------------------
main.cpp          Menu, loading, matching and app flow
Models.h          Student and Group class declarations
Models.cpp        OOP implementations; Group owns a linked list of members
DSA.h             Queue, HashTable and file-function declarations
DSA.cpp           Circular queue and hash table implementation
FileHandling.cpp  THE ONLY FILE-HANDLING IMPLEMENTATION FILE
students.txt      36 student records
groups.txt        15 group records

COMPILE IN VISUAL STUDIO (g++ / MinGW)
--------------------------------------
g++ -std=c++17 main.cpp Models.cpp DSA.cpp FileHandling.cpp -o TeamNexus

Run: .\TeamNexus.exe (Windows) or ./TeamNexus (Linux/macOS)

IMPORTANT: Keep students.txt and groups.txt in the program's working directory.
The files use pipe-separated fields: ID|Name|Skill1|Skill2. Do not put | in a field.

HASHING
-------
There are two HashTable objects: one for student IDs and one for group IDs.
Each table maps an ID to its index in the corresponding array. The hash function
uses key % 2003. If two IDs map to the same slot, linear probing checks the next
slot (open addressing). Search is average O(1), worst-case O(n).

DSA USED
--------
- Hash table with linear probing for student/group ID lookup
- Circular array queue (FIFO) for join requests
- Singly linked list for each group's members
- Array storage for students and groups (capacity 500 and 200)

OOP USED
--------
- Student and Group classes, private fields and public methods
- Constructors, destructor, copy constructor and assignment operator
- Group has-a linked list of MemberNode objects

DATA PERSISTENCE LIMITATION
---------------------------
Student and group records are loaded from and saved to text files. Accepted group
members and pending join requests currently remain in memory and are not saved.
