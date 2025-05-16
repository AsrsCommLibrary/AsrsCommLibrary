
## What problem does AutoStoreCommLibrary solve?

- [AutoStore](https://www.autostoresystem.com/) provides an impressive set of endpoints to interact with their system. However, to develop against that, you must build your own [interface API](https://www.autostoresystem.com/insights/warehouse-control-systems-wcs-ultimate-guide). This requires a lot of work to implement all possible messages. **AutoStoreCommLibrary** solves that problem by implementing all of the endpoints for you in a simple and straightforward way.

- **AutoStoreCommLibrary** was built with developer experience in mind. Sending and processing messages is quick and easy. You can focus on business logic instead of building API endpoints.

- It also includes simulation environments for the task interface that may reduce the number of licenses required to develop a solution that uses **AutoStore**.

## Why?
- After developing several custom solutions, we asked ourselves, "Can we do better". As a result we created this library to remove all complexity around building the API so we could focus on building the customer requirements instead.

## Terms


Task Interface
: Organizes pick lists into collections of bins that must be retrieved together.

Bin Interface
: Organizes picks by preparing and queueing bins at the workstations.

Log Publisher
: A stream of updates from **AutoStore** for real-time system monitoring.

Production Api
: The endpoints will work against an **AutoStore** running in production.

Simulation Api
: The endpoints will work locally in a development / simulation environment.

#### Features

- **AutoStoreCommLibrary** is ready for use with the Task, Bin, and Log Publisher Interfaces. The Shared messages are under construction.

| Implemented Functions | Bin Interface | Task Interface | Shared Interface |
| ---------- | ------------- | -------------- | ---------------- |
| Production Api | 100% | 100% | 100% |
| Simulation Api | 0% | 100% | 0% |

| % Complete | Log Publisher |
| ---------- | ------------- |
| Production | 60% |
| Simulation | 60% |

**Note:** Internally, the team has developed a Proof-of-Concept to Putaway Inventory and Pick orders using the provided simulation environments for Task Interface and Log Publisher.