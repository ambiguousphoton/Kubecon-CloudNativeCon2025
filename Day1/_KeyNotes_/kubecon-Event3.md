Event 3

------

grpc.io

youtube.com/@grpcio

meeting 
    meetup.com/grpcio
    grpc.io/meet/

------
Pawan Bhardwaj  Sr. Sofware Engineer google, gRPC contributer

Kannan Jayaprakasam 



Service Mesh : collection of hrizontally scalled microservices whose node are connected by network infrastructure that manages the connectivity between them...


2 acc/servers deployed

    us-east1
    us-east2

how client will know which server to connect ... load balancing 

It led to rise of sidecars service mesh trailblazer --- envoy
    Case for sidecars 
    ADV    
        deployed along with container
        single tenat 
        easier to scale and schedule
        
    DiS ADV
        NOT FULLY TRANSPARENT
        UPGRADES ARE A Challange


xDs: The Envoy proxy Api.
    xDs control plane to envoy proxy upstream to donwstream...


xDS with gRPC : gRPC Proxiless can underand config ..
            ..same config for envoy and gRPC

xDS name resolution by default gRPC utilezes DNs for name resolution..... example.com:5002  -> dns://example.com:5002

Bootstrappping 

GRPC_XDS_BOOTSTRAP = /path/to/file.json                             //// location/ path

----------------------------------------------------------------------------------------------------------

Proxyless gRPC service mesh 
        Advantages :
            Red infra complexity
            performnace
            existing gRPC benefits
            compatible control plane

        Drawbacks : couples service mesh with application dev, had to use for non-gRPC workloads.

----------------------------------------------------------------------

xDS : is now more of a universal data plane api (not only envoy proxy)

----------------------------------------------------------------------
Structure of xDS




xDS provides :  data nodel : resource contents 
                transport protocol : mechanism for client to obtain resources.


xDs  Resouce Model in grpc : its all about discovering 

    xDiscovery serrviece-- listener ,route , cluster , endpoints 
    Route Resource
    Cluster Resouce : load balancing policy config .. tls config for connection

    endpoint :    A server instance,
                  health status , 
                  pioritized and weighed list of localities and endpoints.

xDS Load Balancing : 

    resouces are resolved via a XDs NameResolver in GRpC 
    Streaming watch for resouces updates fromthe xDS server
    Tree of xDS load balancers implement load balan amaoung service priorities localities and endpoints 
    Connnections initiated by leaf load blancer
    Load balancing is done as per grpc policy
    

xDS Features Supported in grpc : gloabal loadbalancing 

//////////////////////////////
          IT USES ROUND ROBIN FOR LOAD BALANCING     
///////////////////////////////