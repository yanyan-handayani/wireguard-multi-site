flowchart TB
    subgraph CURRENT["Current Topology - Hub and Spoke"]
        HUB["Cyber 1 Jakarta
WireGuard Hub"]:::hub
        S1["Bekasi Cikarang"]:::site
        S2["Batam"]:::site
        S3["Bandung"]:::site

        HUB --- S1
        HUB --- S2
        HUB --- S3
    end

    subgraph FUTURE["Planned Topology - Mesh / Failover"]
        J1["Jakarta"]:::hub
        C1["Cikarang"]:::site
        B1["Batam"]:::site
        D1["Bandung
Additional Public Endpoint"]:::future

        J1 --- C1
        J1 --- B1
        J1 --- D1
        C1 -. Failover .- B1
        C1 -. Failover .- D1
        B1 -. Failover .- D1
    end

    classDef hub fill:#7b2cbf,color:#fff,stroke:#3c096c,stroke-width:2px;
    classDef site fill:#277da1,color:#fff,stroke:#1d3557,stroke-width:2px;
    classDef future fill:#f8961e,color:#fff,stroke:#bc6c25,stroke-width:2px;
