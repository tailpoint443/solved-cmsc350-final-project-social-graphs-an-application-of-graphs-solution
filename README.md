Download Link: https://assignmentchef.com/product/solved-cmsc350-final-project-social-graphs-an-application-of-graphs-solution
<br>



1.  Specification

The concept of <strong>Social Graph</strong> was introduced by M. Zuckerberg at the first Facebook F8 conference in 2007 when he introduced the Facebook platform to model relationships among internet users.

<h2>Part 1</h2>

<strong> </strong>Consider the attached file <strong>Graph.java</strong> which defines a generic undirected <strong>Graph</strong> class. Design and implement a class <strong>SocialGraph</strong> (in a separate source file <strong>SocialGraph.java</strong>) which extends the class Graph. In a social graph, the vertices (graph nodes) represent people names while the un-directed edges represent the acquaintance relationships between them. Class SocialGraph should define constructor(s) and enhance the behavior of the class Graph by defining the following social graphs’ specific methods:




<ul>

 <li><em>normalizedDegreeOfCentrality</em> calculates and returns the normalized degree of centrality for a given vertex The required value is calculated as: degree(v) / (n-1) where degree(v) represents the number of vertex incident edges and <strong>n</strong> represents the number of graph vertices. For social graphs, a high degree of centrality for a person <strong>v</strong> reflects his/her dominant position in the group or his/her social interaction skills.</li>

</ul>




<ul>

 <li><em>numberOfTrianglesIncidentToVertex, </em>calculates and returns the number of triangles incident to vertex <strong>v</strong>. The algorithm below calculates the number of triangles incident for all graph vertices (<strong>V</strong> is the set of vertices, <strong>E</strong> is the set of edges):</li>

</ul>




foreach v in V                  foreach pair of vertices (p, q) in AdjacencyList(v)                       if (p, q) is in E then add 1 to triangles[v]




<ul>

 <li><em>listOfTrianglesIncidentToVertex</em> calculates and returns the list of triangles incident to vertex <strong>v</strong>. A triangle should be specified by its vertices.</li>

</ul>




<ul>

 <li><em>clusterIndividual</em> for a given vertex <strong>v</strong>, calculates and returns the percentage indicating how close its neighbors are to make a complete graph and is calculated as:</li>

</ul>

[(number of edges connecting <strong>v</strong>‘s neighbor vertices) / (number of edges, potentially connecting  <strong>v</strong>‘s neighbor vertices)] * 100 where:

<ul>

 <li>the number of edges connecting <strong>v</strong>’s neighbor vertices is calculated as:</li>

</ul>

(number of triangles incident to vertex v)

<ul>

 <li>the number of edges, potentially connecting <strong>v</strong>‘s neighbor vertices is calculated as: [degree(v) * (degree(v) – 1)] / 2</li>

</ul>




This value measures how close wrapped are the persons in the social graph around the given person.




<ul>

 <li><em>averageClustering</em> for the social graph is calculated as (the sum applies to all vertices <strong>v</strong> in <strong>V</strong>):</li>

</ul>

(1 / n) * ∑ clusterIndividual (v)

This value indicates the overall density of the social graph.




<ul>

 <li><em>isAcquaintance </em>determines whether two persons supplied as parameters can establish social contact direct or through a chain of transitive acquaintance relationships (in terms of graphs it means that there is a path between the two nodes representing the two persons).</li>

</ul>




Additional (helper) methods and / or instance variables may be defined as necessary.




<h2>Part 2</h2>




Design and implement a driver program <strong>TestSocialGraph</strong> (in a separate source file <strong>TestSocialGraph.java</strong>) for testing the methods implemented in Part 1. The driver program should build a social graph from an input file <strong>data.txt</strong>. After building the social graph, <strong>in a loop,</strong> the program should invite the user to select for execution one of the following operations: (1) <em>normalizedDegreeOfCentrality, (2) numberOfTrianglesIncidentToVertex,</em> (3) <em>listOfTrianglesIncidentToVertex</em>, (4) <em>clusterIndividual</em>, (5) <em>averageClustering</em>, (6) <em>isIndirectAcquaintance</em>,  (7) <em>addVertex</em>, (8) <em>addEdge</em>, (9) <em>printEdges </em>and

(0) <em>exit the loop and the program</em>.

As a result of each operation execution, relevant information should be displayed to the user. For example, as a result of invoking <em>clusterIndividual</em> method, the cluster individual value for the given person should be displayed.




An example of the data input file content, its format and the corresponding social graph layout is shown in the attached file <strong>SocialGraph_Example.pdf</strong>.




The programs should compile without errors.




<strong>Notes</strong>.

<ol>

 <li>You may consider that there are no errors in the input file structure.</li>

 <li>If an operation requires additional information, the user will be prompted to enter it.</li>

 <li>The input file (a simple .txt file) should be generated by the students using a simple text editor such as Notepad.</li>

 <li>Person names (instead of indices) should be used in I/O operations involved by the user interface.</li>

</ol>





