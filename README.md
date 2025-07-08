# ADV SVM Prerequisite

## Assignment Overview
This assignment is a peek into the Solana Virtual Machine (SVM) prerequisites, focusing on code analysis and optimization of the `invoke_context` codebase.

## What I did 
- Analyzed the `agave_invoke_context.rs` codebase
- Annotated and comment on the code
- Identify potential optimization areas
- Develop pseudo-code for potential improvements

## Project Structure
- `My_prereq_solution.rs`: Main solution file
- `agave_invoke_context.rs`: Core codebase for analysis
- `Task`: Project requirements document

##Optimization Areas

### 1. Compute Budget and Metering Optimization
- Implement compute unit allocation
- Develop predictive compute unit estimation
- Added compute unit tracking

#### Compute Budget Optimization Diagram
```mermaid
flowchart TD
    A[Start Transaction] --> B{Check Compute Budget}
    B -->|Budget Sufficient| C[Initialize Compute Meter]
    B -->|Budget Insufficient| D[Reject Transaction]
    C --> E[Execute Instructions]
    E --> F{Compute Units Remaining?}
    F -->|Yes| G[Continue Execution]
    F -->|No| H[Halt Execution]
    G --> I[Update Compute Meter]
    I --> E
    H --> J[Return Instruction Error]
    
    subgraph Proposed Optimization
    K[Implement Dynamic Compute Unit Allocation]
    L[Use Predictive Compute Unit Estimation]
    M[Add Fine-Grained Compute Unit Tracking]
    end
```

### 2. Memory Allocation and Management Optimization
- Implement adaptive memory pooling
- Add predictive memory pre-allocation
- Optimize memory fragmentation handling
- Introduce memory usage heuristics

#### Memory Allocation Optimization Diagram
```mermaid
flowchart TD
    A[Memory Allocation Request] --> B{Check Available Memory}
    B -->|Sufficient Memory| C[Align Memory Address]
    B -->|Insufficient Memory| D[Allocation Failure]
    C --> E[Allocate Memory Block]
    E --> F[Update Memory Pointer]
    F --> G[Return Memory Address]
    
    subgraph Proposed Optimization
    H[Implement Adaptive Memory Pooling]
    I[Add Predictive Memory Pre-allocation]
    J[Optimize Memory Fragmentation Handling]
    K[Introduce Memory Usage Heuristics]
    end
```

### 3. Syscall Context and Tracing Optimization
- Implement lightweight tracing mechanism
- Add selective trace logging
- Optimize context switching overhead
- Introduce trace compression

#### Syscall Context Optimization Diagram
```mermaid
flowchart TD
    A[Syscall Invocation] --> B[Prepare Syscall Context]
    B --> C{Validate Syscall Parameters}
    C -->|Valid| D[Execute Syscall]
    C -->|Invalid| E[Reject Syscall]
    D --> F[Log Trace Information]
    F --> G[Update Syscall Context]
    G --> H[Return Syscall Result]
    
    subgraph Proposed Optimization
    I[Implement Lightweight Tracing Mechanism]
    J[Add Selective Trace Logging]
    K[Optimize Context Switching Overhead]
    L[Introduce Trace Compression]
    end
``` 