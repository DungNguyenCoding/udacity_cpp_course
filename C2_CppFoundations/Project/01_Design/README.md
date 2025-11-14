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
| ... | ... |
| ... | ... |

| **Class methods** | **Detail information** | **Activity Diagram** |
| :--- | :--- | :--- |
| ... | ... | [REF](...) |
| ... | ... | [REF](...) |

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

...

| **Class attributes** | **Detail information** |
| :--- | :--- |
| ... | ... |
| ... | ... |

| **Class methods** | **Detail information** | **Activity Diagram** |
| :--- | :--- | :--- |
| ... | ... | [REF](...) |
| ... | ... | [REF](...) |

### &emsp;1.5. Class `render` <a id="1.5"></a>

...

| **Class attributes** | **Detail information** |
| :--- | :--- |
| ... | ... |
| ... | ... |

| **Class methods** | **Detail information** | **Activity Diagram** |
| :--- | :--- | :--- |
| ... | ... | [REF](...) |
| ... | ... | [REF](...) |

## II. Sequence diagram

[def]: ../01_Design/01_ClassDiagram/ClassModel.png