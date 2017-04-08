![Alt text](https://g.gravizo.com/source/custom_mark10?https%3A%2F%2Fraw.githubusercontent.com%2FFantasticFiasco%2Fgravizo%2Fmaster%2FERROR.md)

<details> 
<summary></summary>
custom_mark10
@startuml;
actor User;
participant "Relay service" as A;
participant "Key/value service" as B;

User -> A: GET /relay/{key};
activate A;

A -> B: GET /store/{key};
activate B;

B -> A: {"key":"{key}", "value":"{value}"};
deactivate B;

A -> User:  {"key":"{key}", "value":"{value}"};
deactivate A;

@enduml
custom_mark10
</details>

![Alt text](https://g.gravizo.com/source/custom_mark11?https%3A%2F%2Fraw.githubusercontent.com%2FFantasticFiasco%2Fgravizo%2Fmaster%2FERROR.md)

<details> 
<summary></summary>
custom_mark11
@startuml;
actor User;
participant "Relay service" as A;
participant "Key/value service" as B;

User -> A: GET /relay/key;
activate A;

A -> B: GET /store/key;
activate B;

B -> A: "key":"key", "value":"value";
deactivate B;

A -> User:  "key":"key", "value":"value";
deactivate A;

@enduml
custom_mark11
</details>