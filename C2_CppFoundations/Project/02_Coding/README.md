# OpenStreetMap Route Planner Implementation (Coding)

> [Project Starter Repository](https://github.com/udacity/CppND-Route-Planning-Project)

The [implemation.diff](./implemation.diff) details changes between the modified and original versions of the project. For the full project, please refer [here](./Build%20an%20OpenStreetMap%20Route%20Planner.zip)

```diff
diff --git a/src/main.cpp b/src/main.cpp
index 8becb63..cad4455 100644
--- a/src/main.cpp
+++ b/src/main.cpp
@@ -51,16 +51,66 @@ int main(int argc, const char **argv)
         else
             osm_data = std::move(*data);
     }
-    
-    // TODO 1: Declare floats `start_x`, `start_y`, `end_x`, and `end_y` and get
-    // user input for these values using std::cin. Pass the user input to the
-    // RoutePlanner object below in place of 10, 10, 90, 90.
+
+    // Get start and end points' coordinate from user input
+    float start_x, start_y, end_x, end_y;
+    do {
+        std::cout << "Enter start x:\t";
+        std::cin >> start_x;
+        if (std::cin.fail() || start_x < 0 || start_x > 100) {
+            std::cin.clear();
+            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
+            std::cout << "Error: Value must be between 0 and 100. Please enter again!" << std::endl;
+        }
+        else {
+            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
+        }
+    } while (start_x < 0 || start_x > 100);
+
+    do {
+        std::cout << "Enter start y:\t";
+        std::cin >> start_y;
+        if (std::cin.fail() || start_y < 0 || start_y > 100) {
+            std::cin.clear();
+            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
+            std::cout << "Error: Value must be between 0 and 100. Please enter again!" << std::endl;
+        }
+        else {
+            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
+        }
+    } while (start_y < 0 || start_y > 100);
+
+    do {
+        std::cout << "Enter end x:\t";
+        std::cin >> end_x;
+        if (std::cin.fail() || end_x < 0 || end_x > 100) {
+            std::cin.clear();
+            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
+            std::cout << "Error: Value must be between 0 and 100. Please enter again!" << std::endl;
+        }
+        else {
+            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
+        }
+    } while (end_x < 0 || end_x > 100);
+
+    do {
+        std::cout << "Enter end y:\t";
+        std::cin >> end_y;
+        if (std::cin.fail() || end_y < 0 || end_y > 100) {
+            std::cin.clear();
+            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
+            std::cout << "Error: Value must be between 0 and 100. Please enter again!" << std::endl;
+        }
+        else {
+            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
+        }
+    } while (end_y < 0 || end_y > 100);
 
     // Build Model.
     RouteModel model{osm_data};
 
     // Create RoutePlanner object and perform A* search.
-    RoutePlanner route_planner{model, 10, 10, 90, 90};
+    RoutePlanner route_planner{model, start_x, start_y, end_x, end_y};
     route_planner.AStarSearch();
 
     std::cout << "Distance: " << route_planner.GetDistance() << " meters. \n";
diff --git a/src/route_planner.cpp b/src/route_planner.cpp
index 280ca96..e0f497b 100644
--- a/src/route_planner.cpp
+++ b/src/route_planner.cpp
@@ -8,77 +8,81 @@ RoutePlanner::RoutePlanner(RouteModel &model, float start_x, float start_y, floa
     end_x *= 0.01;
     end_y *= 0.01;
 
-    // TODO 2: Use the m_Model.FindClosestNode method to find the closest nodes to the starting and ending coordinates.
-    // Store the nodes you find in the RoutePlanner's start_node and end_node attributes.
+    // Get the closet nodes to to the starting and ending coordinates
+    start_node = &m_Model.FindClosestNode(start_x, start_y);
+    end_node = &m_Model.FindClosestNode(end_x, end_y);
 
 }
 
-
-// TODO 3: Implement the CalculateHValue method.
-// Tips:
-// - You can use the distance to the end_node for the h value.
-// - Node objects have a distance method to determine the distance to another node.
-
 float RoutePlanner::CalculateHValue(RouteModel::Node const *node) {
-
+    return node->distance(*end_node);
 }
 
-
-// TODO 4: Complete the AddNeighbors method to expand the current node by adding all unvisited neighbors to the open list.
-// Tips:
-// - Use the FindNeighbors() method of the current_node to populate current_node.neighbors vector with all the neighbors.
-// - For each node in current_node.neighbors, set the parent, the h_value, the g_value. 
-// - Use CalculateHValue below to implement the h-Value calculation.
-// - For each node in current_node.neighbors, add the neighbor to open_list and set the node's visited attribute to true.
-
 void RoutePlanner::AddNeighbors(RouteModel::Node *current_node) {
-
+    // Populate current_node.neighbors vector with all the neighbors
+    current_node->FindNeighbors();
+    // Set the parent, the h_value, the g_value
+    for (RouteModel::Node* neighbor_node: current_node->neighbors){
+        neighbor_node->parent = current_node;
+        neighbor_node->h_value = CalculateHValue(neighbor_node);
+        neighbor_node->g_value = current_node->g_value + current_node->distance(*neighbor_node);
+        neighbor_node->visited = true;
+        open_list.emplace_back(neighbor_node);
+    }
 }
 
-
-// TODO 5: Complete the NextNode method to sort the open list and return the next node.
-// Tips:
-// - Sort the open_list according to the sum of the h value and g value.
-// - Create a pointer to the node in the list with the lowest sum.
-// - Remove that node from the open_list.
-// - Return the pointer.
-
+// <REFERENCE> Sorting with a Lambda Expression with sort() method: https://en.cppreference.com/w/cpp/algorithm/sort
 RouteModel::Node *RoutePlanner::NextNode() {
-
+    // Sort the open_list according to the sum of the h value and g value
+    sort(open_list.begin(), open_list.end(), [](const RouteModel::Node* a, const RouteModel::Node* b){
+                                                 return (a->g_value + a->h_value) > (b->g_value + b->h_value);
+                                             });
+    // Get the node with the lowest sum and remove it from the open_list
+    RouteModel::Node* next_node = open_list.back();
+    open_list.pop_back();
+    return next_node;
 }
 
-
-// TODO 6: Complete the ConstructFinalPath method to return the final path found from your A* search.
-// Tips:
-// - This method should take the current (final) node as an argument and iteratively follow the 
-//   chain of parents of nodes until the starting node is found.
-// - For each node in the chain, add the distance from the node to its parent to the distance variable.
-// - The returned vector should be in the correct order: the start node should be the first element
-//   of the vector, the end node should be the last element.
-
+// <REFERENCE> Reversing with reverse() method: https://en.cppreference.com/w/cpp/algorithm/reverse
 std::vector<RouteModel::Node> RoutePlanner::ConstructFinalPath(RouteModel::Node *current_node) {
     // Create path_found vector
     distance = 0.0f;
     std::vector<RouteModel::Node> path_found;
 
-    // TODO: Implement your solution here.
-
+    // Iteratively following the chain of parents of nodes until the starting node is found
+    RouteModel::Node* parent_node = current_node->parent;
+    while(parent_node != nullptr){
+        path_found.emplace_back(*current_node);
+        distance += current_node->distance(*parent_node);
+        current_node = parent_node;
+		parent_node = current_node->parent;
+    }
+    path_found.emplace_back(*current_node);
+    // Reverse the path_found in the order: from start node to the end node
+  	std::reverse(path_found.begin(), path_found.end());
+  
     distance *= m_Model.MetricScale(); // Multiply the distance by the scale of the map to get meters.
     return path_found;
 
 }
 
-
-// TODO 7: Write the A* Search algorithm here.
-// Tips:
-// - Use the AddNeighbors method to add all of the neighbors of the current node to the open_list.
-// - Use the NextNode() method to sort the open_list and return the next node.
-// - When the search has reached the end_node, use the ConstructFinalPath method to return the final path that was found.
-// - Store the final path in the m_Model.path attribute before the method exits. This path will then be displayed on the map tile.
-
 void RoutePlanner::AStarSearch() {
     RouteModel::Node *current_node = nullptr;
 
-    // TODO: Implement your solution here.
-
+    current_node = start_node;
+    open_list.emplace_back(current_node);
+    current_node->visited = true;
+  
+    while(!open_list.empty()){
+      // Check if the search has reached the end_node or not
+      if(current_node->distance(*end_node) == 0){
+        // Store the final path that was found after reaching the end_node
+        m_Model.path = ConstructFinalPath(current_node);
+        return;
+      }
+        // Add all of the neighbors of the current node to the open_list
+        AddNeighbors(current_node);
+        // Sort the open_list and return the next node
+        current_node = NextNode();
+    }
 }
\ No newline at end of file
```