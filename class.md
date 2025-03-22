```mermaid
classDiagram
    AgentDeSecurite -- Incident : intervient
    AgentDeSecurite -- CameraSurveillance : surveille
    Incident -- SystemeAlerte : déclenche
    Incident -- Usager : est signalé par
    Incident -- RapportIncident : génère
    RapportIncident -- ResponsableRATP : est envoyé à
    Transport -- Conducteur : est conduit par
    Transport -- Usager : transporte
    Transport -- Incident : concerne

    class AgentDeSecurite {
        +int id
        +String nom
        +String prenom
        +patrouiller(): void
        +intervenirIncident(): void
    }

    class CameraSurveillance {
        +int id
        +String emplacement
        +activerSurveillance(): void
        +detecterMouvement(): void
    }

    class Incident {
        +int id
        +String type
        +String description
        +DateTime dateHeure
        +declarerIncident(): void
    }

    class SystemeAlerte {
        +int id
        +String typeAlerte
        +envoyerAlerte(): void
        +recevoirRapportIncident(): void
    }

    class Usager {
        +int id
        +String typeUsager
        +String fréquence
        +signalerIncident(): void
    }

    class RapportIncident {
        +int id
        +String details
        +DateTime dateRapport
        +envoyerRapport(): void
    }

    class ResponsableRATP {
        +int id
        +String nom
        +String poste
        +analyserRapportIncident(): void
        +prendreDecision(): void
    }

    class Transport {
        +int id
        +String typeTransport
        +String ligne
        +transporterPassagers(): void
    }

    class Conducteur {
        +int id
        +String nom
        +String prenom
        +conduireTransport(): void
        +signalerProbleme(): void
    }
```
