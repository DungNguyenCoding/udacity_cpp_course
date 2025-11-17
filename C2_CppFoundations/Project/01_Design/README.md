# OpenStreetMap Route Planner Implementation (Design)

## I. Class diagram

### &emsp;1.1. Class dependency <a id="1.1"></a>

| **Class name** | **Detail information** | **Reference** |
| :--- | :--- | :--- |
| `model` | Structure for storing and managing OpenStreetMap. It includes nodes, ways, roads railway and multipolygons |  [REF](#1.2) |
| `route_model` | Inherits from Model, adding the properties and methods needed to perform a specific route search | [REF](#1.3) |
| `route_planner` | The entire logic of A*search and its supporting functions | [REF](#1.4) |
| `render` | All displays to users | [REF](#1.5) |

![ClassDependency](../01_Design/01_ClassDiagram/ClassDependency.png)

### &emsp;1.2. Class `model` <a id="1.2"></a>

![ClassModel](../01_Design/01_ClassDiagram/ClassModel.png)

| **Class attributes** | **Detail information** |
| :--- | :--- |
| m_Nodes | Stores all the coordinate points (Nodes) of the map |
| m_Ways | Stores all the waypoints (Ways) of the map |
| m_Roads | Store all road objects |
| m_Railways | Stores all railway objects |
| m_Buildings | Stores all building objects |
| m_Leisures | Stores all recreation objects |
| m_Waters | Stores all water area objects |
| m_Landuses | Stores all land use objects |
| m_MinLat | Minimum latitude of map area before normalization |
| m_MaxLat | Maximum latitude of map area before normalization |
| m_MinLon | Minimum longitude of map area before normalization |
| m_MaxLon | Maximum longitude of map area before normalization |
| m_MetricScale | Scale factor used to normalize coordinates. It represents the length (in meters) of the shorter side of the map area (after projection) normalized to 1.0 |

| **Class methods** | **Detail information** | **Activity Diagram** |
| :--- | :--- | :--- |
| Model | Initializes the map model. It receives raw OSM data (as XML) and loads/processes it | [REF](...) |
| MetricScale | Returns the value of `m_MetricScale`, which converts the normalized distance back to meters | [REF](...) |
| Nodes | Returns a reference to a vector containing all the `Nodes` | [REF](...) |
| Ways | Returns a reference to a vector containing all `Ways` | [REF](...) |
| Roads | Returns a reference to a vector containing all `Roads` | [REF](...) |
| Buildings | Returns a reference to a vector containing all `Buildings` | [REF](...) |
| Leisures | Returns a reference to a vector containing all `Leisures` | [REF](...) |
| Waters | Returns a reference to a vector containing all `Waters` | [REF](...) |
| Landuses | Returns a reference to a vector containing all `Landuses` | [REF](...) |
| Railways | Returns a reference to a vector containing all `Railways` | [REF](...) |
| AdjustCoordinates | Adjust and normalize raw OSM latitude/longitude coordinates to metric x and y coordinates and bring them to a normalized range (0.0 to 1.0) based on `m_MetricScale` | [REF](...) |
| BuildRings | Handles `Multipolygons` defined by non-closed or segmented `Ways`. This function joins `Ways` together to form closed loops | [REF](...) |
| LoadData | Parses raw OSM (XML) data and fills all member vectors with data | [REF](...) |

### &emsp;1.3. Class `route_model` <a id="1.3"></a>

![ClassRoute_Model](../01_Design/01_ClassDiagram/ClassRoute_Model.png)

| **Class attributes** | **Detail information** |
| :--- | :--- |
| ... | ... |
| ... | ... |

| **Class methods** | **Detail information** | **Activity Diagram** |
| :--- | :--- | :--- |
| ... | ... | [REF](...) |
| ... | ... | [REF](...) |

### &emsp;1.4. Class `route_planner` <a id="1.4"></a>

![ClassRoute_Route_Planner](../01_Design/01_ClassDiagram/ClassRoute_Planner.png)

| **Class attributes** | **Detail information** |
| :--- | :--- |
| ... | ... |
| ... | ... |

| **Class methods** | **Detail information** | **Activity Diagram** |
| :--- | :--- | :--- |
| ... | ... | [REF](...) |
| ... | ... | [REF](...) |

### &emsp;1.5. Class `render` <a id="1.5"></a>

![ClassRoute_Route_Planner](../01_Design/01_ClassDiagram/ClassRender.png)


| **Class attributes** | **Detail information** |
| :--- | :--- |
| ... | ... |
| ... | ... |

| **Class methods** | **Detail information** | **Activity Diagram** |
| :--- | :--- | :--- |
| ... | ... | [REF](...) |
| ... | ... | [REF](...) |

## II. Sequence diagram
