Event 2

Google Cloud Event ::: Abdel Sghiouar ::: Senior Cloud Dev @Google
- Intro to Kro
- Kubernetes Architecture
    Kuberenet Control Plane/ Master :its josbstore the curr state of the cluster and make decision to move the cluster to its desired state.
                        its single node but horizontally scallable
                    
                kubernetes is : Declarative

                    designed specifically for managing state not events or RPCs

                    support standdardized verbs post put get delete list watch
                    resource defination specifies shape of data

                    Creating a new resource API : Customer Resource Definition

                    Schema specifies desired state ...


                    Kubernetes Api Server --> Api for rsouces
                    PUT/apis/example.google.com/v1/counters/my-counter{value: 40} --> Config store (etcd)


                    Controllers listens to specific type of object and it does some thing ...

                    CRD _ OPerator 

                    operator = controller + associated CRDs (resource type) 
                    


                    Managing Cloud Resouces as Kubernetes

                        platform admin --> creates resouces -->intances of CRDs are expanded into k8s resouces -> k8 resources  [othrer k8 operators] --> other cloud services..



                    
    Writing, Maintaining an managing CRDs and Operators could be challanging ----> Kro helps to define Customer User definition.

    Uses :: Resource Graph Definition  (RGD)  ---> metadata- name,
                                                     Schema - apiversion, kind, spec, status ,
                                                     Resources
        Resouce --> what gets created.

    KRO  expamle use Case 1: webapplication Definition
    kubernetes cluster-- WebAppRgd (Devops eng uses kro to crate mange and monitor usage of the WebappRGD RGD) -- instances of the webapp crd expand into k8s resouces   -->Kuberneetes resouces [kcc resources ] --> google cloud api

    Kube Resouce Orchestrator (kro ) + kcc
        kro can be used to define simple and secure develper interfaces for any cloud service . It is an  OSS Project being developed by google, aws and microsoft.
     


    KRo is still in experimental mode still in alpha...

    KRO + KCC




