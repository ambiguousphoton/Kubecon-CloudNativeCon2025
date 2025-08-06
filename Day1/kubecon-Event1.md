KubeConf + CloudNative Conf. Day 1:  4000+ attendees .

Event 1: 

Trends in Cloud native
1. Observability:
	Open Telemetry
	JAEger

2. Platform engineering is mainstream :
	Flux
	Argo Flux
	
	-> Built by Community for Community :
		Expert led Development
		Vendor Neutral 
		Community Driven.


3. Cloud native is taking Ai to production :
	cut clinical validation time form 10 Horus to 20 mins
	Scaled to 1600 CPU , 3.2TB Ram
	
	Kubernetes, Kubeflow
	
———————————————————————————————--------------------------------

First Contribution in CNCF : https://contribcard.cncf.io    // one of 

To Contribute.—> Kebernetes gRPC Clinic

Local CNCG community meet-ups throughout the year

———————————————————————————————---------------------------------

Introducing the Kubernetes Certified AI platform Conformance Program Beta.

Who can apply ::: —— CNF member offering AI/ML
LFX mentorship

———————————————————————————————---------------------------------

- Staff System Engineer Bhavani , ZScaler

  -   Jankiram MSV ( Jankiram & Associates )AI operating System
		——> Kubernes is very important for scaling AI (LLMS)
			Resource abstraction: Gpu , TPUS and emerging accelerators as first class citizens

			Workload diversity: training, fine-tuning, inference and agents in one platform.
			Enterprise Rediness
			
            New Infrastructure :
                Agents - apps ,
                Mcp - data,
                Models - Inference, 
                Accelerated Compute - Infrastructure


			GPU  utilisation could be done efficiently through kuberneties

			Kubernetes leads in Inference.	kubeflow, serve, queue 
								llm-d , vllm , Nvidia Dynamo 
			DATA & MCP INFRASTRUCTURE
				ragpipelines
				Native kubernetis vector database


			Multi Agent Orchestration
				Kagent
				Google ADK
				CrewAi
				Auto Gen2
				LangChain
				LlamaINdex
			
			Orchestration Architecture.





- Isha Gosai & Aditya Gosai ( Expedia Group ) :::: How they scale ArgoCD's Repo-Server to handle 30k applications :::

    Overview    
        inhouse , multi tenat , self Managed kubernetes platform 
                100s of eks clusters, 1000s of EC2s /Nodes, 12000+ a
                Repo Server: Grpc serviece , fetches and renders helm /plain yaml, manifests from git ,, supplies rednerd manifest to the application controller , runs as a sidecar or as a centtralized component.


                Tool Argod, 11 kubernetes clusters.
        Understanding the Challange
        Scalability Architechure
            Tested the repo servers with differenet loads and configuration ::: key tools == Datadog (source monitoring), splunk (event analyis), redis + reposerver
                test low load , no parallism ----- > test 3 10pods
                    Result
                        - helm pull operation cause cpu utilisation..
                        see growth in replcas in cache refresh., during rest days avg resource usage is remains low it is used for pods
                        - Scaling out repo  server pods reduces pressure and imporves distribution
  

- Atulpriya Sharma , Platform Engineer. DX is new ux                 


    Winners in Services where developers are customers 

        F(ind)::::: Be discoverable --- seo , be where the develoopers hangout , use developers language, stack overflow presence, slack, documentation hubs.
        I(vestigate):::: Lead with Technical truths , clearity about product.
        R(un)::::  Be easier to run, make it easy to intall , curl | bash , docker run.. developers needs guidence
        S(hip)::: Observability should be high, load tested, structured logs , graceful failures , secret management, resource limits
        T(ransform)::: DevRel Team, community presence , your developers must become your advocates User Spotlights

        **Know your developer**

- Vishvas Parshuram Chitale CEO Chitale Group ) , and Dipreet Bindra ( Sr Director Engineer Broadcom // VMware's Parent )    || From Grass to Glass Applications,  Chitale Diary
                                            hear mosre custorme storices \\\ see more demos..
       
       
        Build an Agile, Open and Automated Eco-System

        Static Decision : Moved to Modern prv cloud choose kubernetes as platform
                          Modern app built using vshpere kubernetes servie




-----------------------------------------------------------------------------------------------------------------------------

- CNCF Ambasadors Session
    Danial ( Principal Devloper Advocate IBM, Senprincipal Devloper advocate Red hat )

    Qualifications to become ambassador
        Active contribution to a cncf project
        Community leadership
        Public speaking 
        Mentorship
        Content creation

    Why : Recognition for expertise and contribution to comm.
          Network with equally pasionate ambassador globally
          Receive support funding and training from the cncf for hosting events speaking creating content or mentoring others
          partner with Cncf staff to gain insight and provide input to community initiatives
          Global Audience.

------------------------------------------------------------------------------------------------------------------------------



