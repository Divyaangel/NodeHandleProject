# NodeHandleProject
# Node-Based Pipeline Editor

This project involves the creation of a node-based pipeline editor with frontend and backend integration. The project is split into four main parts:

- **Part 1: Node Abstraction**
- **Part 2: Styling**
- **Part 3: Text Node Logic**
- **Part 4: Backend Integration**

Each part builds upon the previous one, culminating in a fully functional node-based pipeline editor that integrates with a backend.

## Overview

### Part 1: Node Abstraction

- **Objective**: Refactor the existing nodes (Inputs, Outputs, LLMs, Text) into a more efficient and reusable abstraction.
- **Solution**: The node abstraction was created by consolidating common logic and using reusable components for shared functionality. This allows new nodes to be easily added without duplicating code.
- **Demonstration**: Five new nodes were created using the abstraction, showcasing its flexibility and efficiency.

### Part 2: Styling

- **Objective**: Create a unified and appealing design for the various components of the pipeline editor.
- **Solution**: Custom styling was implemented to provide an intuitive and visually consistent UI. The design follows a modular approach, where styles can be easily applied or modified across components.
- **Technologies Used**: Custom CSS, React libraries for styling.

### Part 3: Text Node Logic

- **Objective**: Enhance the functionality of the `Text` node.
- **Improvements Made**:
  1. **Dynamic Resizing**: The width and height of the `Text` node automatically adjust as more text is entered, providing better visibility.
  2. **Variable Support**: Users can define JavaScript variables within the text input by using double curly braces (e.g., `{{ input }}`). When recognized, a corresponding Handle is added to the node's left side, representing the variable.
  
### Part 4: Backend Integration

- **Objective**: Connect the frontend with a Python/FastAPI backend to process pipeline data.
- **Frontend Changes**: Updated the `/frontend/src/submit.js` to send node and edge data to the backend via the `/pipelines/parse` endpoint.
- **Backend Changes**: Updated `/backend/main.py` to:
  1. Calculate the number of nodes and edges in the pipeline.
  2. Check if the pipeline is a Directed Acyclic Graph (DAG).
  3. Return a response in the following format:
     ```json
     {
       "num_nodes": int,
       "num_edges": int,
       "is_dag": bool
     }
     ```
- **Frontend Alert**: An alert is triggered upon receiving the backend response, displaying the number of nodes, edges, and whether the pipeline is a DAG.

## Getting Started

### Prerequisites

Make sure you have the following installed on your machine:

- Node.js and npm (for frontend development)
- Python 3.x (for backend)
- Git (for version control)

### How to Use
- Create nodes and connect them to form a pipeline.
- Click Submit to send the pipeline data to the backend.
- View the alert showing the number of nodes, edges, and whether the pipeline is a DAG.

### Future Improvements
- Add more sophisticated error handling on both frontend and backend.
- Improve the UI design based on user feedback.
- Add support for more node types and features.

