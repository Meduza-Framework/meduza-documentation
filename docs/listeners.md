## Overview

The Listeners are one of the core components of Meduza. They handle inbound and requests to/from agents. The Listener component is constructed from a several parts for lifecycle management, database operations and external listener management. 

To learn how to operate the listeners, visit the [Listener API documentation](listener-api.md)

## Authentication

- UI Endpoints: Require standard user authentication via JWT token
- External Listener Endpoints: Require listener-specific authentication


## Listener Kind

|Kind|Description|
|----|-----------|
|http|Default HTTP/HTTPS based listener.|
|tcp|Default TCP based listener.|
|smb|Default SMB protocol based listener (for pivoting).|
|external|External listener. Managed separately but registered with the teamserver. The kind depends on what listener is registered. If a discord listener, kind will be ``discord``.|

## Listener States

|State|Description|
|-----|-----------|
|pending|No resources created, waiting for signal to start.|
|ready|Idle, waiting for initialization/start.|
|starting|Listener is in the process of starting.|
|running|Listener is active and accepting connections.|
|stopping|Listener is in the process of stopping.|
|terminating|Resources are being cleaned up.|
|failed|Operation failed, requires cleanup and restart.|
