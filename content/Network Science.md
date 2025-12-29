## 1. Network Projection

> **Network Projection** --> Transforming a 2-mode network into a 1-mode network. 

This transformation is done in network analysis because 2-mode networks are hard to analyze because they don't have as many analysis methods or network descriptors.

### Characteristics and Implications

- **Bipartite Networks:** A two-mode network consists of two distinct, disjoint sets of nodes (U and V), where links exist only between a U-node and a V-node, not within the same set. Examples of two-mode networks include scientific collaboration networks (scientists and papers) or the Human Disease Network (diseases and genes).
- **Resulting Structure:** A significant consequence of network projection is that the resulting one-mode network often consists of **large fully-connected groups**. This occurs because all nodes connected to a single node in the two-mode structure become linked to each other in the one-mode projection.
- **Bias in Metrics:** This characteristic can introduce biases, especially affecting metrics like clustering coefficients, which rely on the existence of triangles (three connected nodes).

### 1.1. Methods of Network Projection
#### 1.1.1. Binary Method
The simplest way to do network projection. You select one group of nodes (say, people) and draw a line (link) between any two people if they were both connected to the _same_ item in the other group (say, attending the _same_ event or writing the _same_ paper). The final link is binary, meaning it's either **present (1)** or **absent (0)**, regardless of how many items they shared.

> [!question] How to do projection via Binary Method?
> 1. Choose the set of nodes you want to project (e.g., people A, B, C).
> 2. For every pair of nodes (A and B, A and C, B and C), check if they share a connection to **at least one** node of the other type (e.g., an event or a paper).
> 3. If they share at least one, draw a link between them. The resulting network consists of only your chosen nodes and the new links.
#### 1.1.2. Weighted Binary Method (Co-occurrence Counting)
Similar to the binary method, but instead of just drawing a line, you count how many items (co-occurrences) the two nodes shared. The resulting link is **weighted**, and that weight shows the strength of their connection.

> [!question] How to do projection via Weighted Binary Method?
> 1. Choose the two nodes you are calculating the connection for (e.g., Author $i$ and Author $j$).
> 2. Identify all the common items (e.g., papers) they both participated in.
> 3. Sum up the number of these common items. This sum is the weight ($w_{ij}$) of the new link between $i$ and $j$.

**Formula:** The weight of the link ($w_{ij}$) is the sum ($\sum$) of occurrences ($p$) they share: $$w_{ij} = \sum_{p} 1$$
*Where $p$ represents the nodes of the other kind (e.g., papers) that nodes $i$ and $j$ are connected to (their co-occurrences).*
#### 1.1.3. Newman Method
This method is commonly used for collaboration networks and recognizes that collaborating on a paper with only one other person creates a stronger bond than collaborating on a paper with _twenty_ other people. It assigns a weight to the link based on shared items, but reduces the value of that tie according to the size of the original group (number of authors) that produced the item.

> [!question] How to do projection by Newman Method?
> 1. For two nodes ($i$ and $j$), look at one shared item (paper $p$).
> 2. Count the total number of participants ($N_p$) on that shared item.
> 3. The contribution of that single item to the link's weight is calculated as $1/(N_p - 1)$. If the item had 2 authors, the contribution is $1/(2-1) = 1$. If it had 5 authors, the contribution is $1/(5-1) = 0.25$.
> 4. Sum the contributions from all shared items to get the total link weight ($w_{ij}$).

**Formula:** The method for calculating collaboration weight is given as: $$w_{ij} = \sum_{p} \frac{1}{N_{p} - 1}$$ *Where $N_p$ is the number of authors (nodes) on paper $p$.*

#### 1.1.4. Weighted Newman Method
A generalization of the original method, designed to handle cases where the links in the original 2-mode network already have weights (like number of messages, communication frequency). Similar to the original method, it incorporates reduction for the size of the group ($N_p$), but it also factors in the pre-existing weight of the interaction ($w_{i,p}$) from the two-mode structure.

**Formula:** The weights are calculated based on this approach by using the generalization given in the equation: $$w_{ij} = \sum_{p} \frac{w_{i,p}}{N_{p} - 1}$$ _Where $w_{i,p}$ is the original weight attached to the link from node $i$ to the shared resource $p$ (e.g., weight of $i$'s participation in event $p$)._
#### 1.1.5. Sum Method
It is used when the original two-mode network had **weights** on its links already. When projecting, the new link between two people ($i$ and $j$) is found by summing the specific flow/weight they directed toward the shared item. This method creates a directed, weighted, one-mode network, where the weight from A->B is not necessarily the same as the weight from B->A, shows difference in levels of interaction.

> [!question] How to do projection by Sum method?
> 1. Choose two nodes, $i$ and $j$.
> 2. Identify a shared common item ($p$).
> 3. Look up the original weight of the link from $i$ to $p$ (denoted $w_{i,p}$).
> 4. The new link weight $w_{ij}$ is the sum of these weights across all shared intermediate nodes $p$.

**Formula:** The weighted two-mode network projection is formalized as: $$w_{ij} = \sum_{p} w_{i,p}$$ _Where $w_{i,p}$ is the weight of the $i$-th node to the $p$-th event where $i$ and $j$ participated together.

> [!info] Which projection method is the best
> Choosing the right way to turn a two-mode network into a one-mode network is very important for good analysis.
> 
> Weighted projections are usually better than simple binary (yes/no) ones. But Why?
> - Simple binary projection often creates huge fully-connected clumps, which distorts results (e.g., makes clustering look too high).
> - Weighted methods (like Weighted Binary, Newman, or Sum) keep more of the original information.
> - The **Newman method** is often the best choice because it reduces the strength of ties when many people share the same event or group — this fixes a lot of the bias.

<div style="page-break-after: always;"></div>

## 2. Network Models
A network model is basically a recipe for how a network is formed or behaves. It tells you how nodes connect, why they connect, and what the resulting structure looks like.

They are essential tools in network science used to create a simple, mathematical pattern of something that cannot be seen directly. They allow researchers to show complex systems simply, derive network properties mathematically, and predict system behavior and outcomes.

> [!summary] Random Graph Theory
> The whole **field** of mathematics that studies graphs where edges are placed randomly. It asks questions like: What does a typical random network look like? When do giant clusters appear? What is the average distance between nodes? How many triangles are there by chance?
> 
> So “random graph theory” is the big umbrella subject. ER Random Network Model is a specific model.
### 2.1. ER Random Network Model
<small> Erdős and Rényi Model, 1960 </small>

The oldest and simplest network model. It assumes that nodes connect randomly.
- **How it works** --> You start with $N$ nodes. For every possible pair of nodes, you flip a coin (with probability $p$) to decide if they connect. 
  *Alternatively*, the network can be defined by having $N$ nodes and a specific number of links ($M$), with $M$ links randomly selected from all possible links.
- **What you get:** 
	- Almost every dot ends up with roughly the same number of lines coming out of it
	- No “super-popular” stars or big hubs
	- Everyone is about equally connected
	- You can jump between any two dots in just a few steps (small world)
	- Friends of a friend are almost never friends with each other (very little clumping or triangles)
- **Real-life example** --> Think of a group of strangers randomly bumping into each other and making connections.

> The structure of the resulting graph depends entirely on the value of $p$. The node degree distribution follows a **Binomial Distribution** which implies that the number of nodes with a specific degree rapidly decreases around the average degree, meaning all nodes have nearly the same degree. This is why you do not expect large hubs (highly connected nodes) in an ER random network. The network is also **homogeneously connected** with a short path length and a low clustering coefficient.

### 2. Small-World Model
<small>Watts and Strogatz Model, 1998</small> 

A model created to capture two real-life properties that the ER model could not explain:
high clustering (friends of friends are usually friends) and short path lengths (anyone can be reached in a few steps).
- **How it works** --> Start with $N$ nodes arranged in a ring, each connected to its nearest neighbors (like people only knowing their neighbors). Then with a probability $p$, rewire some links to random nodes, creating long-distance “shortcut” connections.
- **What you get:**
	- Nodes still form tight clusters of local friends.
	- But a few random shortcuts suddenly make the whole network feel very small.
	- You can reach distant nodes quickly even though you mostly connect locally.
	- The network becomes a blend of order + randomness.
- **Real-life example** --> You mostly know classmates, coworkers, neighbors (cluster), but you also know someone in another city or country (shortcut). This random long-distance friend makes the whole world feel “small.”

> When $p = 0$, the network is a perfect ring: extremely high clustering but long path lengths. When $p = 1$, the network becomes similar to an ER random graph: low clustering, small path lengths. For intermediate $p$, the model produces the famous small-world effect: high clustering + short paths at the same time — something ER random networks cannot make.
### 3. Scale-Free Models
Real-world networks like the Internet do not follow random graph connections. Instead, they were found to be **scale-free**, where the node degree distribution follows a **power-law distribution** ($P(k) \sim k^{-\gamma}$). This distribution means that **few nodes (hubs) have many links**, while the majority of nodes have very small numbers of connections. Networks exhibiting this property show a **small average path-length** and a **high clustering coefficient**.
#### A.  BA Scale-free Model
<small>Barabási-Albert Model, 1999</small>

The first simple model that explains why real networks (internet, social media, citations) contain a few **extremely popular hubs** instead of everyone being equally connected.
- **How it works** --> The network **grows over time**: new nodes keep joining. Every new node prefers to attach to nodes that **already have many connections**. The rich get richer.
- **What you get:**
    - A few nodes become super-connected hubs.
    - Most nodes remain with only a few connections.
    - The degree distribution follows a power-law (a hallmark of scale-free networks).
    - The network naturally produces short path lengths.
- **Real-life example:** New websites tend to link to well-known pages (Google, Wikipedia). New social media users tend to follow celebrities first. As a result, popular nodes snowball into enormous hubs.

> It uses **Preferential Attachment** --> The chance of connecting to a node is **proportional to its current degree**, leading to the “rich get richer” effect. However, BA only handles the **addition** of new nodes and does not consider node deletion, edge rewiring, or differences in node quality (fitness).

#### B. Fitness-Based Scale-free Model
<small>Bianconi and Barabási</small>

A refinement of the BA model that adds the concept of **node fitness**, explaining why some late-arriving nodes can still become highly connected hubs.
- **How it works** --> Every node has a **fitness value** ($\eta_i$) representing how attractive, useful, or competitive it is. New nodes choose to connect based on **degree × fitness**. This means even a new node with high fitness can outcompete an old hub.
- **What you get:**
    - The network still becomes scale-free.
    - But some nodes become popular because of quality, not just age.
    - High-fitness nodes can become hubs very quickly.
- **Real-life example** --> A brand-new YouTuber or TikToker goes viral overnight, not because they’re old in the network, but because their content quality is high (fitness).
#### C. BBV Scale-free Model
<small>Barrat, Barthmeley and Vespignani</small>

A more advanced version of scale-free models that deals not only with **connections**, but also with **how strong** those connections are.
- **How it works** --> Nodes attach preferentially to those with high **strength** ($s_i$), not just degree. Strength represents the **total weight** of a node’s links (its traffic or load). When a new link arrives, existing weights in nearby nodes are redistributed and adjusted.
- **What you get:**
    - Nodes with heavy traffic (“busy nodes”) keep getting busier → “busy get busier.”
    - Both **degree distribution** and **weight distribution** become heavy-tailed.
    - Hubs form that are not only well-connected but also carry **large traffic loads**.
- **Real-life example** --> Airports: Large airports have many routes (degree) and extremely heavy traffic (weight); new airlines prefer connecting to these big hubs.

### Comparison of the Models

| **ER Random Model**                          | **Small-World Model**                                     | **BA Scale-Free Model**                                 | **Fitness-Based Model**                                    | **BBV (Weighted Scale-Free)**                            |
| -------------------------------------------- | --------------------------------------------------------- | ------------------------------------------------------- | ---------------------------------------------------------- | -------------------------------------------------------- |
| Connections are made completely randomly | Mostly local neighbors, with a few shortcut links | New nodes link to popular nodes (“rich get richer”) | New nodes link based on popularity × fitness           | BA model but also grows connection weights           |
| Nodes have similar degree (no big hubs)  | High clustering + short paths                         | Creates big hubs and many small nodes               | Late nodes with high fitness can still become big hubs | Hubs exist and their connections become stronger |
| Low clustering                               | Very high clustering                                      | Low–medium clustering                                   | Similar to BA                                              | Higher weighted clustering                               |
| Node degrees follow a random pattern     | Node degrees mostly regular                               | Power-law (some nodes extremely connected)          | Power-law, shaped also by fitness                      | Power-law for degrees + weights                      |
| No “special” nodes                           | Neighborhood-based groups                                 | Good for social media, web links                        | Good for viral success or sudden popularity                | Good for airline networks, traffic, trade                |

<div style="page-break-after: always;"></div>

## 3. Robustness and Vulnerability of Complex Networks

Complex systems show a remarkable ability to keep working even when individual components have failed. The main example of this is the Internet: hundreds of routers may malfunction simultaneously, yet global information flow remains stable.

This raises the fundamental question of **Where does this robustness come from, and how does network topology influence it?**

> [!example] Real World Evidence
> Research across various domains indicates that many real-world networks—including communication systems, biological processes, and social structures—are surprisingly resilient to random errors. Examples include:
> - **Technological:** Internet router networks and Autonomous System (AS) networks.   
> - **Biological:** Cellular and metabolic networks.
> - **Social/Organizational:** Terrorist networks.
### 1.1. The Influence of Topology: Random vs. Scale-Free

The architecture of a network decides how its behaves under stress. The most important difference lies between **Random Networks** and **Scale-Free Networks**.

|                     | **Scale-Free Networks**                                                                       | **Random Networks**                                                                                                         |
| ------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| **Structure**       | Heterogeneous degree distribution: many low-degree nodes and a few highly connected hubs      | Homogeneous degree distribution: nodes have similar degree and importance                                                   |
| **Random Attack**   | **Robust** — random failures usually hit low-degree, non-critical nodes; network stays intact | **Moderately Vulnerable** — no special resilience like scale-free networks; random failures affect structure more uniformly |
| **Targeted Attack** | **Highly Vulnerable** — removing hubs rapidly breaks the network and reduces traffic capacity | **Robust** — since no node is uniquely critical, targeted removal does not cripple the network quickly                      |
| **Nature**          | Dual nature: extremely robust to randomness but fragile to targeted attacks                   | Uniform: no special weakness, no special strength                                                                           |

> **Node removal** impacts robustness wayyy more than **Link Removal** because removing a node eliminates all its connected links.
### 1.2. Measuring Robustness
To quantify robustness, researchers simulate damage and measure how the network's structural properties change. This is useful for networks with weighted links and a relatively small number of nodes.

**The General Procedure**
1. **Simulation:** Remove a specific percentage of links (e.g., 5%, 10%, or 20%) randomly.
2. **Repetition:** Repeat the experiment multiple times (e.g., 20 runs) to ensure statistical reliability.
3. **Measurement:** Calculate centrality metrics before and after the removal to assess impact.

Key Metrics --> **Degree**, **Strength**, **Closeness Centrality**, and **Betweenness Centrality**.

> [!summary] Weighted Betweenness Centrality
> To understand the load on specific nodes, the following expression is used for weighted betweenness, where $h$ represents the number of shortest paths:
> $$C_B^{W^\alpha}(k) = \sum_{i \neq j} \frac{h_{ij}^{W^\alpha}(k)}{h_{ij}^{W^\alpha}}$$

> [!info] Spearman Rank Correlation
> To compare the "true" network (original state) against the "damaged" network. It compares the **ranking** of nodes based on centrality (e.g., Betweenness or Closeness) rather than raw values. High Correlation shows the network is structurally stable; the most important nodes remain important even after failures.

<div style="page-break-after: always;"></div>

## 4. Link Prediction in Complex Networks
A fundamental challenge in network science. The goal is to estimate the likelihood of a connection forming between two nodes that are not currently connected.

Formally introduced by **Liben-Nowell and Kleinberg**, this problem focuses on understanding how networks evolve using "endogenous information": predicting future behavior based purely on the network's existing shape instead of external attributes.

> [!question] Why it matters?
> Since most real-world networks (social, biological, technological) are dynamic and constantly growing, link prediction is essential for:
> - **Forecasting Evolution:** Predicting which pairs of nodes (e.g., people, routers) will form links in the future.  
> - **Recovering Missing Data:** Identifying connections that exist but are missing from the dataset due to incomplete sampling.
> - **Analyzing "Dark" Networks:** Uncovering hidden relationships in covert or criminal networks where data is intentionally obscured.
> - **Technological Optimization:** Predicting future data sharing or communication patterns between routers or servers.

### 4.1. Methods of Link Prediction
Most prediction methods rely on **structural similarity**, based on the fact that nodes with similar structural patterns are more likely to connect. These methods are generally divided into **Local** and **Global** indices.
### 4.1.1. Local Indices Measures
Local indices are computationally efficient because they rely only on the immediate neighborhood (connected peers) of the target nodes.
#### A. Common Neighbors (CN)
Used as a baseline benchmark for other methods, CN operates on the simple fact that two nodes sharing many friends are likely to become friends themselves. It counts the intersection of neighbors between node $x$ and node $y$.

**Formula**: Where $\Gamma(x)$ represents the set of neighbors for node $x$ $$Score(x, y) = |\Gamma(x) \cap \Gamma(y)|$$
#### B. Jaccard Index
Used in information retrieval, the Jaccard Index refines the Common Neighbors approach by normalizing it. It measures the ratio of shared neighbors to total neighbors. It penalizes nodes that have a very high degree (too many connections), ensuring the similarity score isn't inflated just because a node is popular.

**Formula**: $$J(x, y) = \frac{|\Gamma(x) \cap \Gamma(y)|}{|\Gamma(x) \cup \Gamma(y)|}$$

#### C. Adamic–Adar Index (AA)
Made to measure similarity between personal homepages on the World Wide Web, this index refines the concept of common neighbors by weighting rare connections more heavily than common ones. A common neighbor that has very few other connections is considered more significant than a "hub" neighbor that connects to everyone.

**Logic:** It uses the inverse log frequency.
- If a common neighbor connects to only 2 people, the weight is high: $\frac{1}{\log(2)} \approx 1.4$.
- If a common neighbor connects to 5 people, the weight drops: $\frac{1}{\log(5)} \approx 0.62$.
### 4.1.2. Global Indices Measures
Global indices consider the entire topological structure of the network, not just immediate neighbors.
#### A. Katz Index
While Local indices look at direct neighbors (paths of length 2), the Katz index sums the ensemble of all paths connecting two nodes, exponentially penalizing longer paths.


<div style="page-break-after: always;"></div>

## 5. Two Mode Clustering
Process of finding the tendency of nodes to form tightly connected groups in a **two-mode network**. 

> [!bug] The Main Challenge in Two-Mode Clustering
> In a two-mode network, nodes only connect **across** the two groups (like people → events), never **within** the same group. Because of this, a node’s neighbors can’t be connected to each other, so triangles can’t form at all. Since normal clustering measures depend on triangles, you can’t use standard (one-mode) local or global clustering coefficients on two-mode networks.
### 5.1. Approaches to Two-Mode Clustering

1. **Network Projection** --> You convert a 2-mode network into a 1-mode network so you can use normal clustering measures. But this often creates big fully-connected groups, which messes up the results; especially anything that depends on triangles.
2. **Specially Designed Measures** --> To avoid these problems, researchers created new clustering formulas made just for 2-mode networks so the results aren’t biased.

> [!summary] Two-Mode Clustering Reinforcement, Robins & Alexander, 2004
> It counts how many **4-cycles** exist compared to how many **3-paths** exist. A 4-cycle basically means two nodes of the same type took part in the **same two events**. But the problem is that this doesn’t measure real **triadic closure** (closure among _three_ nodes). It only shows how strongly **two nodes** are connected through events, not how a group forms. Also, it only works with **binary links** (no weights).
### 5.2. Global Two-Mode Clustering Coefficient
It fixes the above issue by measuring closure among **three nodes** in the main node set. It replaces the usual “triplets” with **4-paths** (open structures) and **closed 4-paths** (closed structures).  

**Weighted Two-Mode Clustering Coefficients**
Opsahl also extended both global and local measures to handle **weights**.

1. **Weighted Two-Mode Global Coefficient** --> Each 4-path gets a **value** based on its link weights. There are 5 methods:
	1. **Binary** --> Pretends all connections are equal. Only cares if the links exist, not how strong they are.
	2. **AM (Arithmetic Mean)** --> Takes the normal average of the two link weights. Treats “strong + weak” the same as “two medium”.
	3. **GM (Geometric Mean)** --> Uses the “balanced” average (square root of product). Punishes pairs where one link is much weaker than the other.
	4. **Min (Minimum)** --> Only counts the weaker of the two links. Very strict – the whole pair is only as good as its weakest part.
	5. **Max (Maximum)** --> Only counts the stronger of the two links. Very generous – one strong tie makes the whole pair look good.
2. **Weighted Two-Mode Local Coefficient** --> The local coefficient looks at **4-paths centered on one node**. The first and last nodes of the 4-path must be in the **same node set** as the focal node. This measure was also extended to use **weighted 4-path values**.

> [!question] Which two-mode clustering co-efficient method is the most accurate?
> The **Geometric Mean (GM)** method is considered the most accurate for two-mode clustering because it handles strong and weak link weights in a balanced, realistic way. It’s the standard used in most modern research and software.


<div style="page-break-after: always;"></div>

## 6. Shortest Paths
The fundamental measurement of distance within a network. It is used as an underlying metric for centrality measures like betweenness and closeness.

> The **shortest path** between two nodes ($i$ and $j$) is the path containing the fewest number of links. This path length is referred to as the distance, $d_{ij}$.

> [!info] Shortest Paths in Unweighted Networks
> In an unweighted network, all links are treated equally. The distance between two nodes depends only on **how many steps** it takes to get from one to the other.
> - If two nodes are directly connected → distance = **1**
> - If you must pass through other nodes → distance = the **smallest number of steps** needed 
> To find this shortest route, algorithms like **Breadth-First Search (BFS)** are used, because they naturally explore the network level by level and find the minimum number of steps.

> [!warning] Shortest Paths in Weighted Networks
> Finding shortest paths is harder when links have **weights**. You can’t just count how many links are in a path, because:
> - A **longer path** with **strong links** might be better than
> - A **shorter path** with **weak links**.
>
> In weighted networks, a link with a **high weight** means a **strong connection**, so it should be treated as a **shorter** or “easier” step. To handle this, we use **Dijkstra’s algorithm** (1959), which finds the path with the **least total cost**. But Dijkstra works only when **low cost = good link**, so we must **invert** the weights:
> 
> $$\text{cost} = \frac{1}{\text{weight}}$$
> 
> - Strong link (high weight) → **low cost**
> - Weak link (low weight) → **high cost**
> 
> Then Dijkstra’s algorithm finds the path whose **total inverted cost** is smallest. The weighted shortest-path distance between nodes (i) and (j) is:
> $$d^W(i, j) = \min\left(\frac{1}{w_{i,h}} + \dots + \frac{1}{w_{h,j}} \right)$$

> **Average Path Length** --> The average of the shortest paths between all pairs of nodes in the network.

> **Network Diameter** --> The LONGEST **shortest path** length found in the entire network. We basically find all the shortest paths and then the longest of those paths is the diameter.

> [!question] Difference between Binomial Distribution and Power Law Distribution
> They describe two very different ways networks can be connected.
> 
> 
| **Binomial Distribution**                                                 | **Power-Law Distribution**                                 |
| ------------------------------------------------------------------------- | ---------------------------------------------------------- |
| Appears in ER random networks.                                            | Appears in Scale-Free networks.                            |
| It is bell-shaped (starts and ends at the bottom and peaks in the middle) | It is long, heavy tailed (like a slope going down forever) |
| - Most have same degree<br>- No Hubs                                      | - Some have a very high degree<br>- Hubs Exist             |
| Rarely matches real networks                                              | Fits many real systems                                     |
| “Almost everyone is average”                                              | “A few kings, millions of peasants”                        |

## Formulas
### 1. Degree and Strength
$$
\begin{align}
\text{Degree} \implies \sum_{j=1}^N{a_{ij}} \\
\text{Strength} \implies \sum_{j=1}^N{w_{ij}}
\end{align}
$$
**Opsahl's Tuning Parameter**
$$
C^{W\alpha}_{D}(i) = deg_{i} \times \left( \frac{str_{i}}{deg_{i}} \right)^\alpha
$$
#### 1.2. Node Indegree and Outdegree from Adjacency Matrix
$$
\begin{align}
\text{Indegree from Adjacency Matrix} = \sum_{i=1}^n{A_{ij}} \\
\text{Outdegree from Adjacency Matrix} = \sum_{j=1}^n{A_{ij}}
\end{align}
$$

### 2. Shortest Path
$$
d{(i,j)} = min(x_{ih} + \dots + x_{hj})
$$
where $d(i,j)$ is the distance between nodes $i$ and $j$. The nodes that come inbetween those are $h$.
#### 2.1. Djikstra's Algorithm
$$
d^W(i,j) = min\left( \frac{1}{w_{ih}} + \dots + \frac{1}{w_{jh}}\right)
$$
**Opsahl's Tuning Parameter**
$$
d^{W\alpha}(i,j) = min\left( \frac{1}{(w_{ih})^\alpha} + \dots + \frac{1}{(w_{jh})^\alpha}\right)
$$

### 3. Betweenness and Closeness
$$
\begin{align}
&\text{Betweenness} \implies C_{B}(i) = \sum_{j}^N \sum_{k}^N \frac{g_{jk}(i)}{g_{jk}} \\
&\text{Closeness} \implies C_{C}(i) = \left[ \sum_{j}^N{d(i,j)} \right]^{-1}
\end{align}
$$

**Opsahl's Tuning Parameter**
$$
\begin{align}
&C_{B}^{W\alpha}(i) = \sum_{j}^N \sum_{k}^N \frac{g_{jk}^{W\alpha}(i)}{g_{jk}^{W\alpha}} \\
&C_{C}^{W\alpha}(i) = \left[ \sum_{j}^N{d^{W\alpha}(i,j)} \right]^{-1}
\end{align}
$$

### 4. Transitivity

$$
\text{Global Clustering Co-efficient} \implies G_{c} = \frac{3 \times \Delta}{\text{triplets}} = \frac{\text{closed triplets}}{triplets} = \frac{\tau\Delta}{\tau}
$$
where $τ$ is the number of 2-paths, and $τ∆$ is the number of these 2-paths that are closed by triangle.

$$
\text{Local Clustering Co-efficient} \implies C(i) = \frac{\text{No of actual links}}{\text{No of possible links}} = \frac{\tau_{i}\Delta}{\tau}
$$

### 5. Two-Mode Networks

$$
\text{Density} \implies N_{D} = \frac{\text{No of available links}}{N_{p} \times N_{s}}
$$

## 1. Representation of Networks
We can represent the same network in 4 ways:

1. **Graph Representation**
![[NS-FigRep.excalidraw]]

2. **Adjacency Matrix**
$$
\begin{bmatrix}
Node && A & B & C & D & E\\
\\
A && 0 & 1 & 0 & 1 & 0\\
B && 1 & 0 & 1 & 0 & 1\\
C && 0 & 1 & 0 & 1 & 0\\
D && 1 & 0 & 1 & 0 & 0\\
E && 0 & 1 & 0 & 0 & 0\\
\end{bmatrix}
$$

3. **Edge List**
$$
(A,B) \ (A,D) \ (B,C) \ (B,E) \ (C,D)
$$

4. **Adjacency List**
$$
\begin{align}
&A \to B, D \\
&B \to A, C, E \\
&C \to B, D \\
&D \to A, C \\
&E \to B
\end{align}
$$
---
## 2. Degree and Strength Centrality

Find the "center-most" (central) node of this network:
![[NS-Fig1.excalidraw | 100%]]

We can create this table by seeing which node to connected to which other nodes.

| Node | is connected to            | Degree | Strength   | $d \times {(s/d)}^\alpha$  |
| ---- | -------------------------- | ------ | ---------- | -------------------------- |
| A    | B (2)                      | 1      | 2          | $1 * (2/1)^{0.5} = 1.414$  |
| B    | A (2), C (3), D (2), E (5) | 4      | 2+3+2+5=12 | $4 * (12/4)^{0.5} = 6.928$ |
| C    | B (3), D (1)               | 2      | 3+1=4      | $2 * (4/2)^{0.5} = 2.828$  |
| D    | B (2), C (1), E (3), F (2) | 4      | 2+1+3+2=8  | $4 * (8/4)^{0.5} = 5.656$  |
| E    | B (5), D (3), F (4)        | 3      | 5+3+4=17   | $3 * (17/3)^{0.5} = 7.098$ |
| F    | D (2), E (4)               | 2      | 2+4=6      | $2 * (6/2)^{0.5} = 3.464$  |
Now, according to **Degree Centrality**, B and D are the center-most since they have the highest degree but, according to **Strength Centrality**, E is the center-most since it has the highest strength.

We can instead use Opsahl's Degree and Weight Centrality
- If we put $\alpha = 0$ our result completely depends on Degree.
- If we put $a = 1$ our result completely depends on Strength.
- For a neutral result we can put $\alpha = 0.5$.

In column 5, we got E having the highest value (7.098) so according to Opsahl's formula E is the center-most.

---
## 3. Betweenness and Closeness Centrality

Find the center-most node of this network:
![[NS-Fig2.excalidraw | 100%]]

If we use **Degree Centrality** for this network then it says that B, C, D are center-most... but we can visually tell that **C** is more central than B and D. Hence, we'll use Betweenness and Closeness Centralities instead:

| Node | possible shortest paths    | paths that go through | Betweenness |
| ---- | -------------------------- | --------------------- | ----------- |
| A    | 6 (BC, BD, BE, CD, CE, DE) | 0                     | $0$         |
| B    | 6 (AC, AD, AE, CD, CE, DE) | 3 (AC, AD, AE)        | $3/6$       |
| C    | 6 (AB, AD, AE, BD, BE, DE) | 4 (AD, AE, BD, BE)    | $4/6$       |
| D    | 6 (AB, AC, AE, BC, BE, CE) | 3 (AE, BE, CE)        | $3/6$       |
| E    | 6 (AB, AC, AD, BC, BD, CD) | 0                     | $0$         |

| Node | distances to other nodes       | sum          | Closeness |
| ---- | ------------------------------ | ------------ | --------- |
| A    | AB (1), AC (2), AD (3), AE (4) | 1+2+3+4 = 12 | $1/12$    |
| B    | BA (1), BC (1), BD (2), BE (3) | 1+1+2+3 = 10 | $1/10$    |
| C    | CA (2), CB (2), CD (2), CE (2) | 2+2+2+2 = 8  | $1/8$     |
| D    | DA (3), DB (2), DC (1), DE (1) | 3+2+1+1 = 10 | $1/10$    |
| E    | EA (4), EB (3), EC (2), ED (1) | 4+3+2+1 = 12 | $1/12$    |
Now we just pick the node with the highest number which is **C**, by both Betweenness (4/6) and Closeness (1/8)

---
## 4. One-Mode and Two-Mode Degree

We have this graph of a network
![[NS-FigBiPart.excalidraw | 100%]]

This network can be divided into 2 disjoint (no-overlapping) sets of nodes:
- $\text{Set 1} = \{A, G, H, I, J, K\}$
- $\text{Set 2} = \{ B, C, D, E, F \}$

Hence, it is a Bipartite Graph. We can easily find the **Two-Mode Degree** of all nodes by counting their neighbors but to find the **One-Mode Degree** we would have to count all the neighbors of neighbors of a node.

| Node | neighbours    | 2-Mode Degree | neighbours of neighbours | 1-Mode Degree |
| ---- | ------------- | ------------- | ------------------------ | ------------- |
| A    | B, C, D, E, F | 5             | G, H, I, J, K            | 5             |
| B    | A, G, H       | 3             | C, D, E, F               | 4             |
| C    | A, I          | 2             | B, D, E, F               | 4             |
| D    | A, I          | 2             | B, C, E, F               | 4             |
| E    | A, J, K       | 3             | B, C, D, F               | 4             |
| F    | A, K          | 2             | B, C, D, E               | 4             |
| G    | B             | 1             | A, H                     | 2             |
| H    | B             | 1             | A, G                     | 2             |
| I    | C, D          | 2             | A                        | 1             |
| J    | E             | 1             | A, K                     | 2             |
| K    | E, F          | 2             | A, J                     | 2             |

**A** has the highest 2-mode as well as 1-mode degree.

---
## 5. Global Clustering Co-efficient

We have this graph
![[NS-FigGCC.excalidraw]]

We can calculate the **Global Clustering Co-Efficient** by dividing the total number of closed triplets (3-points that make a triangle) by the total number of open triplets (3-points that don't make a triangle) as well as closed.

- **Closed Triplets** = 6
	- Triangle 1: A->B<-C, A->C<-B, B->A<-C
	- Triangle 2: B->C<-D, B->D<-C, C->B<-D
- **Open Triplets** = 8
	- A->B<-D, A->C<-D, A->C<-E
	- B->C<-E, D->C<-E
	- C->E<-G, C->E<-F
	- G->E<-F

**Global Clustering Co-Efficient** = 6/14 = 0.42

---
## 6. Weighted Global Clustering Co-efficient

Let's take the same network but this time the edges have weights.
![[NS-FigWGCC.excalidraw]]

There are 4 methods for this: Arithmetic Mean, Geometric Mean, Maximum and Minimum.

| Triplet | Closed? | weights | A.M    | G.M      | Max    | Min    |
| ------- | ------- | ------- | ------ | -------- | ------ | ------ |
| A->B<-C | Yes     | 3,1     | 2      | 1.7      | 3      | 1      |
| A->C<-B | Yes     | 2,1     | 1.5    | 1.4      | 2      | 1      |
| B->A<-C | Yes     | 3,2     | 2.5    | 2.4      | 3      | 2      |
| B->C<-D | Yes     | 1,1     | 1      | 1.0      | 1      | 1      |
| B->D<-C | Yes     | 2,1     | 1.5    | 1.4      | 2      | 1      |
| C->B<-D | Yes     | 1,2     | 1.5    | 1.4      | 2      | 1      |
| A->B<-D | No      | 3,2     | 2.5    | 2.4      | 3      | 2      |
| A->C<-D | No      | 2,1     | 1.5    | 1.4      | 2      | 1      |
| A->C<-E | No      | 2,2     | 2      | 2.0      | 2      | 2      |
| B->C<-E | No      | 1,2     | 1.5    | 1.4      | 2      | 1      |
| D->C<-E | No      | 1,2     | 1.5    | 1.4      | 2      | 1      |
| C->E<-G | No      | 2,1     | 1.5    | 1.4      | 2      | 1      |
| C->E<-F | No      | 2,3     | 2.5    | 2.4      | 3      | 2      |
| G->E<-F | No      | 1,3     | 2      | 1.7      | 3      | 1      |
| **Sum** |         |         | **25** | **22.4** | **32** | **18** |

Now sum all the closed triplets (for each method) and divide by the total.
$$
\begin{align}
&\text{Arithmetic Mean} = \frac{2+1.5+2.5+1+1.5+1.5}{25} = \frac{10}{25} = 0.4\\
&\text{Geometric Mean} = \frac{1.7+1.4+2.4+1.0+1.4+1.4}{22.4} = \frac{9.3}{22.4} = 0.415\\
&\text{Maximum} = \frac{3+2+3+1+2+2}{32} = \frac{13}{32} = 0.406\\
&\text{Minimum} = \frac{1+1+2+1+1+1}{18} = \frac{7}{18} = 0.389
\end{align}
$$

## 7. Newman Projection

> [!question] Question
> Consider the scenario given in the following diagrams based on Newman method of projection in the case of blogs and users who have commented in different blogs.
> $$w_{ij} = \sum_{P} \frac{1}{N_{P}-1}$$
> The nodes with alphabets represent the users and blank nodes represent blogs and groups. Explain the computed weight of links after projection in case of user-blogs interaction.

We are given the graph as well as its resulting graph.

**Graph of Users-Blogs**
![[NS-PP-1.excalidraw]]

- Blog 1: ${A,B}$ → $N_{u_1}=2$ --- contribution $=1$ because $1/(2-1) = 1$
- Blog 2: ${A,B,C}$ → $N_{u_2}=3$ --- contribution $=1/(3-1)=0.5$
- Blog 3: ${B,D}$ → $N_{u_3}=2$ --- contribution $=1$
- Blog 4: ${B,E}$ → $N_{u_4}=2$ --- contribution $=1$
- Blog 5: ${B,E}$ → $N_{u_5}=2$ --- contribution $=1$
- Blog 6: ${E,F}$ → $N_{u_6}=2$ --- contribution $=1$

Add contributions for each pair
- $A-B:$ Blog 1 + Blog 2 = 1 + 0.5 = 1.5
- $A-C:$ Blog 2 = 0.5
- $B-C:$ Blog 2 = 0.5
- $B-D:$ Blog 3 = 1
- $B-E:$ Blog 4 + Blog 5 = 1 + 1 = 2
- $E-F:$ Blog 6 = 1

**Projected Graph of Users-Users**:
![[NS-PP-1-Result.excalidraw]]

**EXPLANATION**
In the Newman projection from **users–blogs** to **users–users**, the weighted link between two users reflects **how strongly they are connected based on commenting on the same blogs**.

The Newman weight formula:
$$
w_{ij} = \sum_{P} \frac{1}{N_P - 1}  
$$

Now the roles are:
- $i, j$ = **users**
- $P$ = **a blog** that both users commented on
- $N_P$ = number of **users** who commented on blog $P$

**What the weights mean**
1. Users become linked when they comment on the same blog. If two users comment on blog (P), that blog contributes weight to their connection.
2. Each shared blog contributes
3. Blogs with _fewer users_ create _stronger links_
4. Total weight = sum of all shared blogs’ contributions