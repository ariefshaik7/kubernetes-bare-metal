# Production-Grade Bare Metal Kubernetes Cluster

A complete guide and manifest collection for deploying a **Highly Available** Kubernetes cluster on bare metal .

--- 
## 🏗 Architecture We use a **Stacked Etcd Topology** with 3 Control Plane nodes ensuring High Availability.

* **High Availability:** **Kube-VIP** runs as a static pod on all Control Plane nodes, managing a floating Virtual IP (VIP) via ARP. 
* **Storage:** **OpenEBS** provides dynamic Persistent Volume provisioning using local disk (LocalPV). 
* **Load Balancing:** * **Layer 4:** **MetalLB** handles IP assignment for Services. 
* **Layer 7:** **Envoy Gateway** handles Ingress, Routing, and Traffic Splitting.

---

## 🛠 Technology Stack 
* **Bootstrapper:** `kubeadm` 
* **Container Runtime:** `containerd` (v2.x) 
* **CNI (Networking):** Calico 
* **CSI (Storage):** OpenEBS (LocalPV Hostpath) 
* **HA Load Balancer:** Kube-VIP (ARP Mode) 
* **Service Load Balancer:** MetalLB (L2 Mode) 
* **Gateway API:** Envoy Gateway


