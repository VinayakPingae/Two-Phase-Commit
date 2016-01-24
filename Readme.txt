Name - Vinayak Subhash Pingale
Email - vpingal1@binghamton.edu

Languages Used - Java

Implementation Details

2 Two-Phase Commit
In the second part, you will implement a replicated remote file service, building on Part 1. The architecture of your replicated file service is very simple: it consists of a single “coordinator” process and multiple “participant” processes:
coordinator the “coordinator” process should expose an RPC interface to clients that contains three methods: writeFile, readFile, and deleteFile. When the coordinator process receives a state-changing operation (write-
File or deleteFile), it uses two-phase commit to commit that state-changing operation to all participants. When the coordinator receives a readFile operation, it selects a participant at random to issue the request
against. The coordinator should be concurrent. It should allow multiple clients to connect to it and should be able to process multiple operations concurrently. participant each participant implements a durable remote file service you built in Part 1. It exposes an RPC interface to the coordinator to participate in two-phase commit. It is up to you what specific methods the participants should support.