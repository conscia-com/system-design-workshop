# Arkitektur-oversigt

> **Note:** Dette er et oplæg til et design som endnu ikke baserer sig på de oprettede workflows. Arkitekturen vil blive
> tilpasset og forfinet baseret på de workflows der identificeres i workshoppen.

Sådan kunne en arkitektur se ud for en automationsplatform med 4 lag. Denne model viser hvordan data og workflows flyder
gennem systemet:

| **LAYER**                               | **Components**                                                                     | **Description / Notes**                                                                                                |
|-----------------------------------------|------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| USER & FRONTEND                         | • User<br>• Frontend (HTML / UI)                                                   | User interacts with the frontend, which communicates with the REST API.                                                |
| REST / API (DMZ)                        | • REST API<br>• Presenter DB (Thin Representation)<br>• Publishes to Message Queue | Stores only a **thin representation** of data — just enough for the UI and queueing. Sends jobs/messages to the queue. |
| WORKER                                  | • Message Queue / Bus<br>• Workflow Engine<br>• Reference DB                       | Queue receives jobs from Layer 2; workflow engine processes them using the reference DB.                               |
| INFRASTRUCTURE<br>**(Source Of Truth)** | • NSO<br>• W.M.<br>• Catalyst C.<br>• NetBox                                       | Backend systems act as the **full SOURCE OF TRUTH**, receiving asynchronous updates from workflows.                    |
