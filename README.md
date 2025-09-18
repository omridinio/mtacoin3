# MTA Coin – Distributed Blockchain Simulation with Docker

This project simulates a simple blockchain-like mining system using **C++** and **Docker containers**.  
It was developed as part of an academic exercise to practice **inter-process communication (IPC)**, containerization, and distributed client–server programming.

---

## 🚀 Features
- **Server + Miner Architecture**  
  - **Server**: validates new blocks, manages subscriptions, and broadcasts blocks.  
  - **Miners**: connect to the server via named pipes, subscribe, mine blocks, and send results back.  

- **Containerized Execution**  
  - Each component runs in its own **Docker container**.  
  - Communication between containers via **named pipes (FIFO)** in a mounted path.  

- **Dynamic Miner Registration**  
  - Each miner creates its own pipe (`miner_pipe_1`, `miner_pipe_2`, etc).  
  - Server automatically responds with the current block.  

- **Configuration & Logging**  
  - Server reads mining difficulty from `CommonFile.conf` in the shared library directory.  
  - Logs are written into `/var/log` inside containers.  

