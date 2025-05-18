## **Overview**

The Listener API in Meduza provides functionality to create, manage, and interact with C2 (Command and Control) infrastructure. This API supports multiple listener types (HTTP, TCP, SMB, and external) and handles their lifecycle.

## **UI endpoints (Client facing)**

*These requests are handled by the frontend. They remain approximately the same for different kinds but the documentation will be using the ``http`` listener for demonstration. To perform the requests, the user* **must be authenticated** *to the teamserver using a JWT token. If the requests are performed using Postman or some other tool (like curl), the user will need to provide an authentication token in the request header as a ``Bearer`` token.*

###**Create a Listener**
Creates a new listener configuration.

**Endpoint:** ``POST /api/v1/listeners``

**Request Body:**
```json
{
  "kind": "http",
  "name": "primary-listener",
  "description": "Main HTTP listener",
  "heartbeat": 60
}
```
**Successful Response:**
```json
{
  "status": "success",
  "message": "Listener created",
  "data": null
}
```

###**Get All Listeners**
Retrieves a list of all configured listeners.

**Endpoint:** ``GET /api/v1/listeners``

**Request Body:**

No body is required to perform the request.

**Successful Response:**
```json
{
  "status": "success",
  "message": "Listeners retrieved successfully",
  "data": [
    {
      "id": "f8d7e9a1-c4b6-4a8c-9e2d-3f5c7b9e8a1d",
      "kind": "http",
      "status": "running",
      "name": "primary-listener",
      "description": "Main HTTP listener",
      "external": false,
      "host": "localhost",
      "port": 8010,
      "heartbeat": 60,
      "config": {... kind specific config ... },
      "created_at": "2024-09-12T15:30:45Z",
      "updated_at": "2024-09-12T15:30:45Z",
      "started_at": "2024-09-12T15:31:05Z",
      "stopped_at": null
    },
...
  ]
}
```

###**Get Listener by ID**
Retrieves a specific listener by ID.

**Endpoint:** ``GET /api/v1/listeners/{listener_id}``

**Request Body:**

No body is required to perform the request.

**Successful Response:**
```json
{
  "status": "success",
  "message": "Listener retrieved successfully",
  "data": {
    "id": "f8d7e9a1-c4b6-4a8c-9e2d-3f5c7b9e8a1d",
    "kind": "http",
    "status": "running",
    "name": "primary-listener",
    "description": "Main HTTP listener",
    "external": false,
    "host": "localhost",
    "port": 8010,
    "heartbeat": 60,
    "config": {},
    "created_at": "2024-09-12T15:30:45Z",
    "updated_at": "2024-09-12T15:30:45Z",
    "started_at": "2024-09-12T15:31:05Z",
    "stopped_at": null
  }
}
```

###**Get Listener by Name**
Retrieves a specific listener by name.

**Endpoint:** ``GET /api/v1/listeners/{listener_name}``

**Request Body:**

No body is required to perform the request.

**Successful Response:**
```json
{
  "status": "success",
  "message": "Listener retrieved successfully",
  "data": {
    "id": "f8d7e9a1-c4b6-4a8c-9e2d-3f5c7b9e8a1d",
    "kind": "http",
    "status": "running",
    "name": "primary-listener",
    "description": "Main HTTP listener",
    "external": false,
    "host": "localhost",
    "port": 8010,
    "heartbeat": 60,
    "config": {},
    "created_at": "2024-09-12T15:30:45Z",
    "updated_at": "2024-09-12T15:30:45Z",
    "started_at": "2024-09-12T15:31:05Z",
    "stopped_at": null
  }
}
```

###**Get Listener Statuses**
Retrieves the status of all listeners.

**Endpoint:** ``GET /api/v1/listeners/statuses``

**Request Body:**

No body is required to perform the request.

**Successful Response:**
```json
{
  "status": "success",
  "message": "Listeners retrieved successfully",
  "data": {
    "f8d7e9a1-c4b6-4a8c-9e2d-3f5c7b9e8a1d": "running",
    "a1b2c3d4-e5f6-7a8b-9c0d-e1f2a3b4c5d6": "ready"
  }
}
```

###**Start Listener**
Start a specific listener.

Endpoint: ``POST /api/v1/listeners/{listener_id}/start``

**Request Body**:

No body is required to perform the request.

**Successful Response:**
```json
{
  "status": "success",
  "message": "Successfully started listener with ID: f8d7e9a1-c4b6-4a8c-9e2d-3f5c7b9e8a1d",
  "data": null
}
```

###**Stop Listener**
Stop a specific listener.

Endpoint: ``POST /api/v1/listeners/{listener_id}/stop``

**Request Body**:

No body is required to perform the request.

**Successful Response:**
```json
{
  "status": "success",
  "message": "Successfully stopped listener with ID: f8d7e9a1-c4b6-4a8c-9e2d-3f5c7b9e8a1d",
  "data": null
}
```

###**Terminate Listener**
Terminate and remove a specific listener.

Endpoint: ``DELETE /api/v1/listeners/{listener_id}``

**Request Body**:

No body is required to perform the request.

**Successful Response:**
```json
{
  "status": "success",
  "message": "Listener deleted successfully",
  "data": null
}
```

###**Update Listener**
Update a listener's configuration.

**Endpoint:** ``PUT /api/v1/listeners/``

**Request Body:**
```json
{
  "id": "f8d7e9a1-c4b6-4a8c-9e2d-3f5c7b9e8a1d",
  "name": "primary-listener",
  "description": "Updated HTTP listener description",
  "config": {
    "read_timeout": 30,
    "write_timeout": 30
  }
}
```

**Successful Response:**
```json
{
  "status": "success",
  "message": "Successfully updated listener f8d7e9a1-c4b6-4a8c-9e2d-3f5c7b9e8a1d",
  "data": null
}
```

## **External Listener Endpoints**

*External listener endpoints are meant for externally deployed listeners to register and integrate themselves with the teamserver*

###**Register External Listener**
Registers an external listener with the teamserver.

**Endpoint:** ``POST /external/register``

**Request Body:**

**Successful Response:**

W.I.P.