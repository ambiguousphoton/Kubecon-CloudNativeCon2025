Bridging Data & ML ecosystems: A cloud Native Approach using Kubeflow

                by:
                    Johnu George Technial Dierector Nutanix AI
                    Shivji Kumar Jha Staff eng. Data platforms Nutanix Ai

/////
github issues : github.com/kubeflow/trainer/issues/2655
/////


Kubeflow Introduction
    
    ML OPs pipeline
        
                                            Model Registry

                A                    A                       A               A                     A
                |                    |                       |               |                     |
        data prepration         --> model devlopment --> model training --> model optimization --> Model Serving
       
       
        kube flowspark operator   kubeflow notebooks   kubeflow trainer    kubeflow katlib         kubeflow pipeline


Single Node ML Training

    storage resource [disk][cleaned dataset] ---load data in parallel-->  prefetch pubber --> model training


Multi Node ML Train

    Load sharded datain parallel

Challenges in Ml stack

    Eficient storage for large datasets
            larger dataset better model

            solution :
                    apache parquet

    Gpu under utilization
            high data throughput req to keep gpu busy

            solution :
                        arrow flight 
                        custom infra for ml trainng


    Sharding data across workers
            Unique subset of data for every worker

            solution :
                        arrow flight 
                        custom infra for ml trainng

    Consistent Shuffing of data across epochs
            Restream data in every epoch
            Network bandwidth wastage


            solution : indexed data storage

    Supporting Heterogeneous training jobs on same dataset.
            I/O wastage due to static data sharding pattern

            solution : Dynamic assignment based on workers






Next Gen DataStack for tackaling Challanges

    ----> Apache Parquet   //// DISC /// Storage Efficieny  
                Compressed columnar storage Format
                Lowest Storage and IO cost


                Arrow format is for that doesnot have to decomprss the data in caching layer
                

        Easy access to Parquet files
    ----> Apache Iceberg
                    S3 means infinite storage & good HA
                    Open Table format (SQL & ACID)
                    Lots of integration 
                    but slow access and transfer cost

    -----> APACHE ARROW    ////  CACHE /// Keepdata such that it is very easily available for gpu to access like storing in cache
                    Cache data in arrow format
                    Efficint in memory storage

                    Workers consuem data from cache

    ------> Arrow Flight : Zero Copy  Transport
            Status Quo : Serializing / Deserializing data at each step
            A Cache built for training workers ;:::::: dynamic allocation of data to workers   //// changes as workers increases asking (N) data chunks  for (N) Workers
        


        Putting it all together
            Data Fusion
                Queries MetaData from Iceberg
                Headnode assigns slice to data nodes
                data nodes fetch stroe data (arrow)
                Pytorch workers fetch req data`