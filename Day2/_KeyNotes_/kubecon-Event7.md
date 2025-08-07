Grafana 


Software for GPU

    - Cpu  data to gpu  + 
    - Gpu data copy to Cpu 


    CPU launch kernel to gpu
    

CPU is orchestrator for GPU tasks

    - Kernels are launched from cpu
    - Memory is allcated and deallocated by CPU

Grafana Beyla is eBPF -based, zerocode,


Why eBPF ?
    allows programs to run within the linux kernel in a sage and efficient manner
    low overhead 
    collect profiles form all nodes 
    zero instrumentation


How ?
    identified imp cuda calls
    added probes and gathered data


Cuda LuanchKernal
    
    SEC('uprobe/cudaLaunch Kernel' ) int BPF_KPROBE(handle_cuda_launch)
    Prometheus Metrics for checking  ----> gridCardinality  focus on optimisations and see dependencies

CudaMalloc //flawed

    SEC("uprobe/cudaMalloc") 
    int BPF_KPROBE(handle_cuda_malloc) 

cudaMemCpy (Host to device , Device to host)

Resources
    - Mirage Persistent Kernel: compiling LLMs into a MegaKernel
    - Look Ma, No bubbles! Designing a low-latency MegaKernel

    Fusing Kernels to make Mega Kernels....... 

    LLama3.2 
    Mega Kernel library to combine and optimise

Profiling 
    Pytorch Kernels 

Limitations with eBPF approach

    Limited information abailable on kernel execution time
    No access to GPU hardware API to measure Temprature , SM utilization, etc

Future
    - More architechures we only have cuda probes right now...
    - Capture context before / after GPU call

A Hitchhiker's Guide to the AI bubble 

Key takeawawys 

    - ebpf canbe  a sol to close between traditional gpu monitering and modern solutions



