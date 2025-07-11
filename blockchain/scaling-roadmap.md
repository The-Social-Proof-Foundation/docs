---
icon: rocket-launch
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Scaling Roadmap

As MySocial prepares to launch its mainnet, we are committed to ensuring that our blockchain infrastructure can scale efficiently to meet increasing user demands. Our current implementation employs the Narwhal and Bullshark protocols to achieve high throughput and low latency. To further enhance performance and aim for a throughput of **1 million transactions per second (TPS)**, we plan to integrate advanced consensus mechanisms, specifically Rorqual and Shoal++.

## Integration of Rorqual

[Rorqual](https://arxiv.org/html/2408.14099v1) is a protocol designed to enhance the performance of DAG-based mempools like Narwhal by integrating Trusted Execution Environments (TEEs). The key benefits of Rorqual include: • Reduced Latency: By leveraging TEEs, Rorqual streamlines the steps required to include a vertex in the DAG, reducing the latency to a single message delay in the best case. • Increased Throughput: The protocol simplifies communication, decreasing complexity and enhancing throughput without incurring significant computational costs. • Enhanced Security: TEEs provide a secure environment for transaction processing, reducing the potential for Miner Extractable Value (MEV) attacks and ensuring data integrity.

## Integration Strategy for Rorqual

To integrate Rorqual into our existing infrastructure, we will undertake the following steps:

1. TEE Infrastructure Deployment: Set up the necessary TEE infrastructure across validator nodes to support Rorqual's requirements. This includes configuring hardware and software components to establish a trusted execution environment.
2. Protocol Integration: Modify the existing Narwhal protocol to incorporate Rorqual's communication mechanisms, ensuring that transactions are processed within the TEE framework. This step requires careful coding and testing to maintain system integrity.
3. Testing and Validation: Perform extensive testing in a controlled environment to validate the integration, focusing on performance metrics such as latency, throughput, and security. This phase ensures that the integration meets our performance goals without compromising security.
4. Deployment and Monitoring: Roll out the integrated system to the mainnet, accompanied by continuous monitoring to promptly identify and address any issues. Ongoing performance assessments will guide further optimizations.

## Integration of Shoal++

[Shoal++](https://arxiv.org/abs/2405.20488) is a DAG-based BFT consensus protocol that offers high throughput while significantly reducing end-to-end latency. Its key features include: • Optimized Latency: Shoal++ reduces commit latency to an average of 4.5 message exchanges, approaching the theoretical minimum for BFT protocols. • High Throughput: By allowing multiple validators to propose blocks in parallel, Shoal++ maximizes network bandwidth utilization and enhances scalability. • Robustness: The protocol is designed to handle network faults gracefully, maintaining performance even under adverse conditions.

## Integration Strategy for Shoal++

To replace the current Bullshark consensus with Shoal++, we will follow these steps:

1. Consensus Layer Modification: Implement Shoal++ within the consensus layer, ensuring compatibility with the existing DAG structure provided by Narwhal (now enhanced with Rorqual). This step requires careful protocol engineering to maintain consensus integrity.
2. Validator Coordination: Update validator nodes to support Shoal++, including changes to block proposal and voting mechanisms. Validators will need to be synchronized to operate under the new consensus rules.
3. Comprehensive Testing: Conduct rigorous testing to validate the new consensus mechanism's performance, focusing on metrics such as transaction finality time, throughput, and fault tolerance. This phase ensures that Shoal++ meets our performance and reliability standards.
4. Mainnet Deployment: Deploy the updated consensus mechanism to the mainnet, with continuous monitoring to ensure stability and performance. Any issues identified post-deployment will be addressed promptly to maintain system integrity.

## Goals and Benefits

By integrating Rorqual and Shoal++ into our blockchain infrastructure, MySocial aims to achieve the following:

* Triple Throughput: Enhance the current system's throughput by a factor of three, moving closer to our goal of **1 million TPS**.
* Reduced Latency: Achieve sub-second transaction finality, providing a seamless user experience.
* Enhanced Security: Leverage TEEs to bolster security against potential attacks, ensuring data integrity and user trust.

Through these strategic integrations, MySocial is poised to become the **fastest blockchain in the world**, ready to meet the demands of a multiple viral social platforms.
