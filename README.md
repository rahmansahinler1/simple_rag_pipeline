# What is RAG pipeline?

"RAG" stands for Retrieval Augmented Generation. A base LLM model is trained on large open source data and it performs poorly on a given specific domain.
We can generate general question answers with them, but interacting a base model with condifential data is not possible.
This problem can be solved with building RAG pipelines.

With RAG we're able to continously feed the model with that specific domain data and it's performance on that topic skyrockets.
Also, we can use private data locally.

With RAG we can benefit LLM's securely & more correctly.
Following are the main benefits for using RAG pipeline

- Interaction with secure data
- Increased accuracy on a specific domain
- Source of information can be addressed
- Internal documents does not needed to uploaded to the web. Local pipeline can be established

In this work, a simple RAG Pipeline established and a PDF file used for question answering.
Used pdf file is a work of group of engineers including me on modeling hybrid electic vehicle on Python environment.
If you're insterested you can checkout the link: https://ieeexplore.ieee.org/document/10415973

For this work both a local llm (llama2:7b) and an open ai model (gpt-3.5-turbo-0125) used.

# Why locally?

- Private Data: You can enable to use your private data without uploading it to the internet.
- Cost: Cost will be dramatically be less if you use llm's locally on a large project.
- Speed: If you have good hardware system, you don't need to establish extra steps. You can just your own system.

# Quick Start - Environment

For this work WSL environment is used.
I highly suggest using linux environment for AI related works for compability.
Following steps needs to be followed to establish the same environment:

- WSL2 Installation (Microsoft store, ubuntu 22.04)
- WSL2 is a must. (You can check wsl version with powershell and this command: wsl -l -v, If you have WSL1 as default you can change it with following instructions on this link: https://learn.microsoft.com/en-us/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package, then you need to upgrade your installed version with this code: wsl --set-version <your ubuntu version> 2)
- OLLAMA (https://ollama.com/download/linux)
- LLAMA2:7B (use this command: ollama pull llama2:7b)
- CUDA (A gpu > gtx 1650, if you've never used cuda follow this steps: https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=WSL-Ubuntu&target_version=2.0&target_type=runfile_local, you can track down you gpu activitiy with following command on terminal: watch -n 1 nvidia-smi)

# Libraries
You can install the necessary libraries with: pip install -r requirements.txt
! I highly suggest to use virtual environment
! Pytorch is just used to check GPU availability. If you have limited space you can delete it from the requirements.txt
