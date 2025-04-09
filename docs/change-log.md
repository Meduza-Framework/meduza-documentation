# Change Log



## **Version 0.4**

New Features and Functionality:

- [ ] **Big** changes to the listener system, featuring a new way of loading external listeners and a revamped service for built-in listeners (HTTP/S, TCP, SMB).
- [ ] **Big** changes to the payload system. Payloads can be loaded no matter the codebase (No longer limited to dotnet only).
- [ ] Made module system specific only to agents with module loading support.
- Help command logic with dynamic loading of commands if modules are installed.
- Jupyter notebook implementation for scripting.
- [ ] Module dependency loading follow load order (only C# agent).
- [ ] Database migration system.
- [ ] New payload compilation types (DLL and Shellcode).
- Improved teams functionality
- [ ] Other module types for the C# Agent (Command, Persistence, Info, etc.).
- [ ] More functionality for the client.
- [ ] SSL/TLS certificate handling and loading.
- [ ] Improved C# Agent functionality (persistence, AV bypass and other important features).


## **Version 0.3**

New Features and Functionality:

- Agent authentication and check-in using the new check-in handler.
- Expanded API functionality (new endpoints for module, payload and agent management).
- Diffie-Hellman key exchange to establish a shared 32 byte key for bidirectional AES-256 encrypted communication using Galois/Counter Mode (GCM) for message integrity.
- Module loading for C# agents.
- Dependency loading during runtime for C# modules.
- DAL logging and error handling improvements.
- Improved unit testing for server components.
- Listener AutoStart functionality.
- Payload service for configuration and compilation of the C# agent.
- Functional listener login pages.
- Improved client authentication.
- "multiplayer" functionality.
- Restructured and cleaned up code structure.


## **Version 0.2 (MVP Expansion)**

New Features and Functionality:

- Migrated persistent storage functionality from Redis to use PostgreSQL only.
- Listener start/stop functionality implementation.
- Basic unit testing to the server component.
- Basic client functionality.
- XOR Encryption/Decryption util.


## **Version 0.1 (MVP)**

New Features and Functionality:

   - Docker compose to run containerized parts of the server.
   - Basic Agent Service system.
   - Basic GO-based utilities.
   - Database implementation using PostgreSQL
   - Client authentication and client related services.
   - Basic listener implementation (models only).
   - Redis for cache and persistent storage.