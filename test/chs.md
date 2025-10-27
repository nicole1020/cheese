# Cheese AI Agent Process Flow

```mermaid
flowchart TD
    A(["Customer Request"]) --> B["Receive Order: Webhook / Msg Start"]
    B --> C{"Cheese OK? (Schema / PII / Policy)"}
    C -- No --> CX["Reject & Notify"] --> Z(["End"])
    C -- Yes --> D["Prep Cheese: Clean / Chunk / RAG"]
    D --> E["Apply Recipe: Prompt Template / Rules"]
    E --> F["Cook: Model Inference + Tools"]
    F --> G{"Taste Test Needed?"}
    G -- Yes --> H["User Review / Edits"]
    H --> G2{"Approved?"}
    G2 -- No --> E
    G2 -- Yes --> I["Plate: Post-process / Format"]
    G -- No --> I
    I --> J["Serve: Deliver to API / SharePoint / Email"]
    J --> K["Log Leftovers: Telemetry / Feedback"]
    K --> L(["End"])
