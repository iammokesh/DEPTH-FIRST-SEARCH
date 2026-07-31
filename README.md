# BREADTH-FIRST-SEARCH

<h1>ExpNo 3 : Implement Breadth First Search Traversal of a Graph</h1>

<h3>Name: MOKESH C</h3>

<h3>Register Number:212225240088</h3>

<h3>Aim:</h3>

<p>To implement Breadth First Search Traversal of a Graph using Python 3.</p>

<h3>Theory:</h3>

<p>
Breadth-First Search (BFS) is a graph traversal algorithm that explores all the vertices at the current depth before moving to the next depth level. Since graphs may contain cycles, a visited array is used to avoid visiting the same vertex more than once. BFS uses a Queue data structure to keep track of the next vertex to visit.
</p>

<h3>Algorithm:</h3>

<ol>
<li>Construct a graph using vertices and edges.</li>
<li>Create an empty queue and mark all vertices as unvisited.</li>
<li>Insert the starting vertex into the queue and mark it as visited.</li>
<li>Remove a vertex from the front of the queue.</li>
<li>Visit all its unvisited adjacent vertices, mark them as visited, and insert them into the queue.</li>
<li>Repeat Steps 4 and 5 until the queue becomes empty.</li>
</ol>

## Program

```python
from collections import deque
from collections import defaultdict

def bfs(graph, start, visited, path):
    queue = deque()

    queue.append(start)
    visited[start] = True
    path.append(start)

    while len(queue) != 0:
        tmpnode = queue.popleft()

        for neighbour in graph[tmpnode]:
            if not visited[neighbour]:
                visited[neighbour] = True
                queue.append(neighbour)
                path.append(neighbour)

    return path

graph = defaultdict(list)

v, e = map(int, input().split())

for i in range(e):
    u, v = input().split()
    graph[u].append(v)
    graph[v].append(u)

start = input()

visited = defaultdict(bool)
path = []

traversedpath = bfs(graph, start, visited, path)
print(traversedpath)
```

### Sample Input and Output
<img width="661" height="292" alt="Screenshot 2026-07-27 143553" src="https://github.com/user-attachments/assets/0b739a0c-0d98-46d1-8199-8e6f005197e9" />
<img width="647" height="210" alt="Screenshot 2026-07-27 143510" src="https://github.com/user-attachments/assets/e00fcf6c-b0c2-481e-bd55-6b1a828a6d8b" />



<h3>Result</h3>

<p>Thus, a graph was constructed and Breadth First Search (BFS) traversal was implemented successfully using Python 3.</p>
