# Simple Python Router

This project implements a basic router in Python, capable of handling routing updates, withdrawals, data messages, and network dumps. The router uses sockets for communication and maintains a routing table to manage routes.

## High-Level Approach

The router is designed to simulate basic functionalities of a network router including establishing connections with neighbors, processing routing updates, and forwarding messages based on the routing table. It utilizes UDP sockets for inter-router communication and JSON for message formatting.

### Key Components:
- **Routing Table**: Stores network routes with attributes like network address, netmask, and next-hop.
- **Message Handling**: Processes different types of messages (`update`, `withdraw`, `data`, and `dump`) received from neighboring routers.
- **Route Selection**: Implements algorithms to select the best route based on various criteria such as local preference, AS path length, origin type, and lowest IP address.

## Challenges Faced

- **Concurrency**: Managing simultaneous incoming messages and ensuring the routing table is updated correctly was a challenge. The solution involved careful management of socket connections and selective processing of messages.
- **Route Selection Logic**: Implementing the route selection process to handle tie-breaks and ensure the most efficient route was chosen required careful consideration of routing policies and attributes.
- **Testing Complex Scenarios**: Simulating real-world routing scenarios to test the router's behavior in various conditions was complex and required meticulous setup of test cases.

## Features and Properties

- **Simplicity**: The router is implemented with simplicity in mind, making it easy to understand and extend.
- **Modularity**: The code is organized into distinct functions for processing different message types, making it modular and maintainable.
- **Flexibility**: The router can easily be extended to support additional message types and routing protocols.
- **Robustness**: Includes basic error handling for socket communication and message processing to ensure stability.

## Testing Overview

Testing was conducted through a series of unit tests and integration tests:

- **Unit Tests**: Focused on individual functions to ensure correctness of operations like CIDR conversion, message processing, and route selection.
- **Integration Tests**: Simulated network environments with multiple routers to test the system's behavior end-to-end. Scenarios included route updates, withdrawals, and handling of data messages.
- **Scenario-Based Testing**: Specific routing scenarios were created to test the router's decision-making in selecting the best routes and handling edge cases.

## Conclusion

This project provided valuable insights into the workings of network routers and the complexities of routing protocols. While the current implementation covers basic functionalities, future enhancements could include support for more sophisticated routing protocols and improved error handling mechanisms.
