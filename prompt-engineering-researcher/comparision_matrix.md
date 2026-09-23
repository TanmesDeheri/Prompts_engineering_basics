| Technology       | Scalability | Setup Complexity | Operational Overhead | Cost Model                                  |
| ---------------- | ----------- | ---------------- | -------------------- | ------------------------------------------- |
| **Kubernetes**   | **High**    | **High**         | **High**             | **Pay-per-node / infrastructure resources** |
| **Docker Swarm** | **Med**     | **Low**          | **Med**              | **Pay-per-node / infrastructure resources** |
| **AWS Fargate**  | **High**    | **Med**          | **Low**              | **Pay-per-use**                             |

**Basis:** Kubernetes documents support for clusters up to 5,000 nodes under specified large-cluster criteria. ([Kubernetes][1]) Docker Swarm scales by adding worker nodes, while managers primarily provide orchestration and consensus; Docker recommends three or five managers for HA and notes that adding managers does not increase scalability. ([Docker Documentation][2]) Fargate uses resource-based, per-second pricing for vCPU, memory, and storage, with no upfront costs. ([aws.amazon.com][3])

*Note: “High/Med/Low” are comparative classifications for this table, not vendor-defined ratings.*

[1]: https://kubernetes.io/docs/setup/best-practices/cluster-large/?utm_source=chatgpt.com "Considerations for large clusters | Kubernetes"
[2]: https://docs.docker.com/engine/swarm/how-swarm-mode-works/nodes/?utm_source=chatgpt.com "How nodes work | Docker Docs"
[3]: https://aws.amazon.com/fargate/pricing/?utm_source=chatgpt.com "AWS Fargate Pricing"
