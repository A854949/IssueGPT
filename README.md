#  IssueGPT 

![image](https://github.com/A854949/IssueGPT/assets/82749575/3ea53440-af3d-419d-ac18-0587467c6b6e)


Issue is an advanced AI-driven tool designed to enhance the efficiency and accuracy of troubleshooting within computer product testing . This system utilizes state-of-the-art Large Language Models (LLMs) to analyze complex issues, predict root causes based on historical data, and suggest viable solutions.

# Prerequisite
1. WSL
2. CUDA
3. CONDA
   
# Installation

* Clone IssueGPT repository
```
  git clone https://github.com/A854949/IssueGPT.git
  cd IssueGPT
```

* Clone llama.cpp repository
```
  git clone https://github.com/ggerganov/llama.cpp
  cd llama.cpp
  make
```

* Install Python 3.11
```
  conda create -n IssueGPT python=3.11
  conda activate IssueGPT
```

* modify IssueGPT/settings.yaml - local to specific your model name
```
poetry install --with ui
poetry install --with local
```

* Run ```python scripts/setup``` to download your model
  
* After that running the following command in the repository will install llama.cpp with GPU support:
```
CMAKE_ARGS='-DLLAMA_CUBLAS=on' poetry run pip install --force-reinstall --no-cache-dir llama-cpp-python
```

* Put your doucuments into ```document``` folder, and run
```
make ingest document
```

* Once installed, you can run IssueGPT with the following command:
```
PGPT_PROFILES=local make run
```

* If your installation was correct, you should see a message similar to the following next time you start the server ```BLAS = 1```.
