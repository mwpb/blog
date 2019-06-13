# Find nearest clone

(Hackerrank 'Find the nearest clone' problem.)

def get_adj_dict(graph_nodes, graph_from, graph_to):
    adj_dict = defaultdict(list)
    for i, start in enumerate(graph_from):
        adj_dict[start].append(graph_to[i])
        adj_dict[graph_to[i]].append(start)
    return adj_dict

def bfs(start, adj_dict, color, visited, color_lookup):
    q = deque([(start, 0)])
    while len(q):
        node, distance = q.pop()
        for next_node in adj_dict[node]:
            if next_node not in visited:
                if color_lookup[next_node] == color:
                    return distance+1, next_node
                visited.add(next_node)
                q.appendleft((next_node, distance+1))
    return -1, None

def get_color_lookup(ids):
    color_lookup = {}
    for i, color in enumerate(ids):
        color_lookup[i+1] = color
    return color_lookup

def findShortest(graph_nodes, graph_from, graph_to, ids, val):
    adj_dict = get_adj_dict(graph_nodes, graph_from, graph_to)
    color_lookup = get_color_lookup(ids)
    try:
        node = ids.index(val) + 1
    except:
        return -1
    visited = set([node])
    out = float('inf')
    while len(visited) < graph_nodes:
        x, node = bfs(node, adj_dict, val, visited, color_lookup)
        if x == -1:
            break
        elif x < out:
            out = x
    return -1 if out == float('inf') else out