# Universal MCP Overview

The Universal MCP system is a framework designed to enable AI models to interact with external systems and APIs. It achieves this through a core set of components: Applications and Actions, supported by an Integration system and Triggers.

**Applications** form the foundation for connecting to external services. They manage aspects like authentication, API communication, defining available operations, and handling responses and errors. The system provides base classes to simplify the creation of new applications, including `BaseApplication` (an abstract base class), `APIApplication` (for HTTP APIs), and `GraphQLApplication` (for GraphQL APIs). Creating a new application involves setting up a specific package structure and implementing a class that inherits from one of these base classes.

**Actions** define the specific operations that an application can perform. These allow AI models to execute external functions, call APIs, process data, and interact with real-world systems. Key features of Actions include dynamic function calling, structured input/output, integration with various authentication methods, error handling, and tool management. Custom actions are created by defining methods within an application class, including type hints and docstrings, implementing error handling, and registering them in the `list_tools()` method.

**Integration** is the mechanism that allows Applications and Actions to work together. It handles authentication, credential management, API communication, and error handling. The system supports several integration types inluding API Key, OAuth, Basic Auth, etc.

**Triggers** act as a notification system, enabling AI agents to respond dynamically to external events from integrated applications like GitHub or Gmail. When specific events occur in these applications, triggers notify the agents.