# Change Log



## **Version 0.4**

New Features and Functionality:

- [ ] **Big** changes to the listener system, featuring a new way of loading external listeners and a revamped service for built-in listeners (HTTP/S, TCP, SMB).
       - Moved the listener system to the listener service folder at `teamserver/internal/services/listener` including built-in listeners.
       - Changed the way listeners are handled (removed tight coupling).
- [ ] **Big** changes to the payload system. Payloads can be loaded no matter the codebase (No longer limited to dotnet only).
       - Modular agent loading no matter the codebase.
       - Dynamic compilation parameter loading for the front-end.
       - Dynamic payload compilation based on payload codebase.
- [ ] Made module system specific only to agents with module loading support.
- Help command logic with dynamic loading of commands if modules are installed.
- Jupyter notebook implementation for scripting.
       - Docker container running Jupyter notebook.
       - Environment variables for Jupyter notebook startup.
- [ ] Module dependency loading following load order (only C# agent).
- [ ] Database migration system.
- [ ] New payload compilation types (DLL and Shellcode).
- Improved teams functionality
- [ ] Other module types for the C# Agent (Command, Persistence, Info, etc.).
- [ ] More functionality for the client.
- [ ] SSL/TLS certificate handling and loading.
       - Endpoints and handler for uploading SSL/TLS certificates to the server.
- [ ] Improved C# Agent functionality (persistence, AV bypass and other important features).


## **Version 0.3**

New Features and Functionality:

- Agent authentication and check-in using the new check-in handler.
- Expanded API functionality (new endpoints for module, payload and agent management).
- Diffie-Hellman key exchange to establish a shared 32 byte key for bidirectional AES-256 encrypted communication using Galois/Counter Mode (GCM) for message integrity.
- Module loading for C# agents.
- Dependency loading during runtime for C# modules.
       - Modules are shipped with dependencies and loaded on the agent.
- DAL logging and error handling improvements.
       - Standardized logging for DALs.
- Improved unit testing for server components.
- Listener AutoStart functionality.
- Payload service for configuration and compilation of the C# agent.
       - Payload service for compiling the agent with different parameters.
- Functional listener and login pages (client).
- Improved client authentication.
       - Standardized middleware.
       - Fixed refresh token functionality.
- "multiplayer" functionality.
       - API endpoints for `teams` CRUD operations.
       - DAL for `teams` DB operations.
       - `team_handler.go` for managing `teams`.
- Restructured and cleaned up code structure.
       - Standardized server return format.
       - Standardized and parametrized API endpoints.


## **Version 0.2 (MVP Expansion)**

New Features and Functionality:

- Migrated persistent storage functionality from Redis to use PostgreSQL only.
- Listener start/stop functionality implementation.
       - `service.go` for listener lifecycle management.
       - Environment variables for listener configuration. 
- Basic unit testing to the server component.
       - Handler unit tests in `/tests/handlers`.
       - Mocks for unit tests in `/tests/mocks`.
- Basic client functionality.
       - Login page, sidebar and custom components.
- Revamped XOR Encryption/Decryption util.
       - Simplified `xor.go` to avoid decorator pattern.
- Custom logger for the server at `/teamserver/pkg/logger`.


## **Version 0.1 (MVP)**

New Features and Functionality:

   - Docker compose and initialization scripts to run containerized parts of the server.
   - Basic Agent Service system.
       - Agent management API endpoints at `/api/v1/agents`
       - `agent_handler.go` for listener side and client side agent changes.
       - SQL queries for `agents`, `agent_config`, `agent_info` and `agent_task` table creation.
       - DAL for agent DB operations.
   - Basic GO-based utilities.
       - `env.go`, `strings.go`, `xor.go`
   - Pgadmin4 for database management.
       - Docker container running pgadmin4.
       - Environment variables for pgadmin4 startup.
   - Database implementation using PostgreSQL
       - Docker container running PostgreSQL.
       - Environment variables for PostgreSQL startup.
   - Client authentication and client related services.
       - JWT based client authentication.
       - API endpoints and middleware for client authentication.
   - Basic listener implementation (models only).
       - Listener models in `teamserver/models/listener.go`
       - SQL query for `listeners` table creation.
       - DAL for listener DB operations.
       - `listener_handler.go` for listener management.
   - Redis for cache and persistent storage.
       - Docker container running redis.
       - Environment variables for redis startup.
   - Live reloading using `Air`.
---