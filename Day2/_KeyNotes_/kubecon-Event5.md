Amarnath Ch and Arthi ,Software Engineers  @Microsoft


Agenda

Multi Cluster Architecture and workload Orchestration

    - Collection of independently running worker cluster managed hrouugh contrl cluster
    - Each Worker cluser resource are represeneed as a namespace in control cluster
    - shared resource hosting multi workloads including webservice ai workloads

        worker Cluster: 
                        Independent ly operated kubernetes cluster , 
                        node pools of various types, 
                        Syncer agent watching to pull the assigned workload and applies locally
                        Reports the status back to control cluster


        Control Plane:
                        Interface to fleet, 
                        Manages Worker Cluster Lifecycle, 
                        Workload Scheduling and Slicing , 
                        Quota Management

Key demands for local storage: specify local storage resource req. 
                        capacity aware provisioning of pods in cluster . 
                        Guaranteed local storage space for lifetime of pod 


    Container Storage Interface:
                            Container Storage Interface CSI :standard for exposing storage systems to containerized workloads on containers orchestration systems like kubernetes

                            CSI Driver: plugin that alllows kuberenetes to provision attach mount and manage storage form storage system 


    Local Storage CLass offereings

        Disks grouped as volume groups which are exposed storage classes 
        storage classmapped to lvm-csi-driver
        Lvm based CSIDriver  /// Logical Volume based
        Each node will have CSI Driver pod
        CSI driver : conforms to csi semantics

    Bootstrappping :
        Each Storage class maps to single or multi volume groups
        disks initalized ot physical volumenspvs belonging to similar types


    Capacity Tracking :


    --------------------------------------------------------------------------------------------------------------------------------------------
                        Worker Cluster                                     ||||                                 Control Cluster

        lv-csi-driver[external-provisioner] ---> csiStorageCapacity --------     ------        --> syncer---> FleetNode CR ---> Uber Scheduler
    --------------------------------------------------------------------------------------------------------------------------------------------






    Capacity Aware Scheduling 

    --------------------------------------------------------------------------------------------------------------------------------------------

    WorkLoad (Deployment, PVC(Local-pvc))  --------> Uber Scheduler  (fileters candidates from list with greedy approach) 
                                                                            |
                                                                            |
                                                                            |
                                                                    Worker CLuster 




    Auditing Volumes 
        Custem Resouce ==== CSI Volumes captures metadatafor volumen reaqest ---- purely for auditing volume lifecycle

    Temporal Storage
        Genric Ephemeral Volumes 

    Local Storage Usage
        Scratch Volumes
            Temporary storg used for imtermidiate data or caching
        
        Config Volumes
            shared across pods used to store config files , models
        
        Log Volumes
            Capture verbose or debug logs that are not pushed to centralized log stores
            Require regular cleanup based on vol size to avoid disk pressure
            usefull for short term diagnistics and troubleshooting

        
    

