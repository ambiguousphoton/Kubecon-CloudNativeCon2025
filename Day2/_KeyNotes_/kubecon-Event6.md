NVIDIA

Cluster API to streamline Kubernetes Clusters LifeCycle Management at NVIDIA
    by::
    
        Megha Singhal,Senior SRE, Cloud Infra
        Gulshan Khatri,Senior SRE, Cloud Infra


Challenges: Silos and Inefficiencies

    - Scatterd Provisioning 
    - Rising Operational Costs
        



CLuster API for declarative Cluster Definition

    user create Enviroment_variable.sh--> clusterctl geerate yaml___bareMetalcluster, bareMaeta... ----> kubectl -f

Custom Clustre API Infrastructure Provider

    Tailored for on perm infrastructure
    Efficient Lifecycle Management
    Seamless Integration

Embracing Heterogeneous Clusters

    CPU, GPU, TEGRA, ARM

Reducing Complexity with Helm

    Wrapping Templates, 
    Single Configurable Point ,
    Simplified Upgrades, 
    Standardized Deployment




Users only need to define and update values.yaml---> GitRepoitory --> Fluxcd applies updates as per state on ( Management Cluster )

Key Takeaways 

    Standardized Operations ----- Fluxcd 
    Declarative Clusters --- in yamlfile  and git as single source of truth
    Operational Efficiency  ---- Removing need of manual cluster management
    Scalability ----- 75+ clusters 
    Security & Complience

    