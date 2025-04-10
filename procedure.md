## Simulator Interface Overview

The simulator is divided into four main tabs:

1. **Setup** - Configure system resources and process requirements
2. **Resource Allocation** - Visualize current resource distribution
3. **Resource Request** - Request additional resources for processes
4. **Simulation** - Run and visualize the algorithm execution


At the bottom of the interface, you'll find the **Action Log** which records all system events.

## Detailed Tab Functionality

### Setup Tab

This tab allows you to configure the initial state of the system:

- **Available Resources**: Set the number of available instances for each resource type (R0, R1, R2)
- **Process Configuration**: Define the maximum resource needs and current allocations for each process

- **Max**: Maximum number of resources a process may request
- **Allocation**: Currently allocated resources to the process
- **Need**: Resources still needed by the process (automatically calculated as Max - Allocation)



- **Check System State**: Run the safety algorithm to determine if the current configuration is in a safe state
- **Reset**: Return the simulation to its initial state


### Resource Allocation Tab

This tab provides a visual representation of the current resource allocation:

- **Available Resources**: Visual display of free resources in the system
- **Process Allocation**: Progress bars showing allocated resources for each process

- The filled portion (red) represents allocated resources
- The number in parentheses (yellow) shows needed resources
- The maximum value is displayed at the end of each bar





### Resource Request Tab

This tab allows you to request additional resources for processes:

- **Make a Request**: Enter the number of resources to request for a specific process
- **Request Button**: Submit the resource request for processing
- **Current State**: View available resources and system status

- If a safe sequence exists, it will be displayed
- If the system is in an unsafe state, a warning will be shown





### Simulation Tab

This tab allows you to run an automatic simulation of the algorithm:

- **Simulation Controls**: Start, pause, and reset the simulation
- **Simulation Speed**: Adjust how quickly the simulation progresses
- **Simulation Progress**: Track which processes have completed and which are pending
- **Resource Visualization**: See how resources are distributed during the simulation
- **Legend**: Color coding for different elements in the simulation


## Step-by-Step Usage Guide

### Basic Usage

1. **Initial Setup**:

1. Start in the **Setup** tab with the default values
2. Review the available resources and process requirements
3. Click "Check System State" to determine if the system is in a safe state



2. **Understanding Resource Allocation**:

1. Navigate to the **Resource Allocation** tab
2. Observe how resources are currently distributed among processes
3. Note the available resources and the needs of each process



3. **Making Resource Requests**:

1. Go to the **Resource Request** tab
2. Select a process and enter the resources you want to request
3. Click "Request" to attempt the allocation
4. Note that requests will only be granted if they maintain the system in a safe state



4. **Running the Simulation**:

1. Navigate to the **Simulation** tab
2. Click "Simulate" to watch processes execute in the safe sequence
3. Observe how resources are released when processes complete
4. Use "Pause" to stop at any point or "Reset" to start over





### Advanced Usage

1. **Creating Deadlock Scenarios**:

1. In the **Setup** tab, modify resource allocations to create a potential deadlock
2. Click "Check System State" to see if the system detects the unsafe state
3. Try to request resources that would lead to deadlock and observe the denial



2. **Analyzing Safe Sequences**:

1. After running the safety algorithm, examine the safe sequence
2. In the **Simulation** tab, observe how following this sequence prevents deadlock
3. Try different initial configurations to generate different safe sequences





## Key Components Explained

### Action Log

The Action Log at the bottom of the screen records all system events chronologically, including:

- Resource allocations and releases
- Process completions
- Safety checks
- Request approvals and denials


This log is essential for understanding the sequence of events and debugging issues.

### Legend

The Legend in the Simulation tab explains the color coding used throughout the simulator:

- **Blue**: Available resources
- **Red**: Allocated resources
- **Green**: Completed processes
- **Yellow**: Currently executing process


### Info Buttons

Throughout the interface, you'll find info buttons (ⓘ) that provide contextual help about specific components when hovered over.

## Tips for Effective Use

1. **Start Simple**: Begin with the default configuration to understand how the algorithm works
2. **Incremental Changes**: Make small changes to see how they affect the system state
3. **Watch the Action Log**: The log provides valuable information about what's happening
4. **Create Edge Cases**: Try to create scenarios where resources are nearly exhausted to see how the algorithm handles them
5. **Experiment with Speeds**: Adjust the simulation speed to better observe the resource allocation process


## Common Scenarios

### Safe State Example

- Default configuration is in a safe state
- Safe sequence: P0 → P2 → P1 → P3 → P4
- All processes can complete without deadlock


### Unsafe State Example

- Allocate most available resources to processes with large maximum needs
- System will detect potential deadlock
- Resource requests that would lead to unsafe states will be denied


