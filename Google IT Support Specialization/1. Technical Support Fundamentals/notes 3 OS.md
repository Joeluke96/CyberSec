# Operating System

An **Operating System (OS)** is system software that manages computer hardware, software resources, and provides common services for computer programs.

## Key Functions of an OS

- **Process Management**: Handles the creation, scheduling, and termination of processes.
- **Memory Management**: Allocates and manages memory for processes.
- **File System Management**: Organizes and controls access to data on storage devices.
- **Device Management**: Manages device communication via drivers.
- **User Interface**: Provides a user interface, such as CLI or GUI.

## Types of Operating Systems

1. **Batch Operating System**
2. **Time-Sharing Operating System**
3. **Distributed Operating System**
4. **Real-Time Operating System**
5. **Mobile Operating System**

## Examples of Operating Systems

- Windows
- macOS
- Linux
- Android
- iOS

## Two Main Parts of an Operating System

1. **Kernel**: The core part of the OS that manages system resources, including CPU, memory, and devices. It operates at a low level and interacts directly with hardware.
   **Kernal Space**
   - **_Process Manager_**
     -The process scheduler is part of the kernel that makes this multitasking possible. It switches the execution of each different process on the CPU faster than you can blink and it gives you the illusion that things are happening simultaneously
   - **_Memory Manager_**
   - Our kernel optimizes memory usage and makes sure our applications have enough memory to run.
   - **_File Manager_**
   - **_I/O Manager_**
     -mportant function that a kernel performs is input, output or IO management. This is how our kernel talks to external devices, like disks, keyboards, networks, connections, audio devices and more. IO management is anything that can give us input or that we can use for output of data.
2. **User Space**: The part of the OS where user applications and utilities run. It provides interfaces and tools for users to interact with the system. We interact with user space directly.
   The user space is everything outside the kernel. These are the things that we interact with directly, like programs such as text editors, music players, system settings, user interfaces, etcetera.

# Files and File Systems

# File Handling

There are three main components to handling files handlers, the **file data, metadata, and file system**

1. # File system

A **file system** is a method and data structure that an operating system uses to control how data is stored and retrieved on a storage device. Without a file system, data would be stored in a single large block with no way to tell where one piece of data ends and the next begins.

### Key Components of a File System

1. **File Structure**: Defines how files are organized and stored.
2. **Directories**: Provide a hierarchical structure to organize files.
3. **Metadata**: Stores information about files, such as name, size, type, and permissions.
4. **File Allocation Table (FAT)**: Tracks the location of files on the storage device.
5. **Access Control**: Manages permissions to ensure security and proper access.

### Types of File Systems

- **FAT32**: Commonly used in USB drives and older systems.
- **NTFS**: Used in Windows systems, supports large files and advanced features like encryption.
- **ext4**: Commonly used in Linux systems, supports journaling and large file sizes.
- **APFS**: Used in macOS, optimized for SSDs and supports encryption.
- **HFS+**: Older macOS file system, replaced by APFS.

### File System Operations

- **Create**: Create new files or directories.
- **Read**: Access the contents of a file.
- **Write**: Modify or add data to a file.
- **Delete**: Remove files or directories.
- **Search**: Locate files or directories within the file system.

### Journaling File Systems

A journaling file system keeps a log (or journal) of changes that will be made to the file system. This helps prevent data corruption in case of a system crash or power failure.

### Mounting and Unmounting

- **Mounting**: The process of making a file system accessible to the operating system.
- **Unmounting**: The process of safely disconnecting a file system from the operating system.

### Importance of File Systems

File systems are critical for data organization, retrieval, and security. They ensure efficient storage and access to data while maintaining system stability and performance.

2. # File data

Another important part of file management is the storage of actual file data. We write data to our hard drive in the form of data blocks. When we say something to our hard disks, it doesn't always sit in one piece. It can be broken down into many pieces and written to different parts of the disk.

## Block Storage

Block storage is a type of data storage where data is stored in fixed-sized blocks. Each block is identified by a unique address, and the operating system manages these blocks to store and retrieve data efficiently.

### Key Features of Block Storage

1. **Flexibility**: Blocks can be used to store any type of data, making it versatile for different applications.
2. **Performance**: Provides high-speed data access, suitable for databases and transactional systems.
3. **Scalability**: Easily scalable by adding more storage blocks.
4. **Independence**: Blocks are independent units, allowing for efficient data management and recovery.

### How Block Storage Works

- Data is divided into fixed-sized blocks.
- Each block is assigned a unique identifier.
- The operating system or storage controller manages the mapping of blocks to physical storage locations.

### Use Cases for Block Storage

- **Databases**: High-performance storage for structured data.
- **Virtual Machines**: Storage for virtual machine disk images.
- **Email Servers**: Efficient storage for large volumes of email data.
- **Backup and Recovery**: Reliable storage for backup systems.

### Advantages of Block Storage

- High performance and low latency.
- Supports advanced features like snapshots and replication.
- Suitable for applications requiring fast and frequent data access.

### Disadvantages of Block Storage

- Requires a file system to organize and manage data.
- Can be more expensive compared to other storage types like object storage.

Block storage is a foundational technology for many enterprise and cloud storage solutions, offering a balance of performance, scalability, and reliability.

3. # File Metadata

## File Metadata

File metadata is data that provides information about other data, specifically files. It describes the attributes and properties of a file, enabling the operating system and applications to manage and interact with files effectively.

### Key Components of File Metadata

1. **File Name**: The name assigned to the file.
2. **File Size**: The size of the file in bytes.
3. **File Type**: The format or type of the file (e.g., .txt, .jpg, .exe).
4. **Creation Date**: The date and time the file was created.
5. **Modification Date**: The date and time the file was last modified.
6. **Access Permissions**: Defines who can read, write, or execute the file.
7. **Owner Information**: Identifies the user or group that owns the file.
8. **File Location**: The path or address where the file is stored on the storage device.

### Importance of File Metadata

- **File Organization**: Helps in categorizing and locating files efficiently.
- **Access Control**: Ensures proper permissions and security for file access.
- **System Operations**: Enables the operating system to manage files effectively.
- **Data Integrity**: Provides information to verify the authenticity and integrity of files.

### Metadata Management

The operating system stores metadata in the file system, often in structures like inodes (in Linux) or Master File Table (MFT) entries (in NTFS). Proper management of metadata is crucial for system performance and reliability.

File metadata plays a vital role in file management, ensuring that files are accessible, secure, and organized within the operating system.

# Process Management in Kernel

Process management is a critical function of the kernel, ensuring efficient execution and coordination of processes within the operating system.

### Key Responsibilities of Process Management

1. **Process Scheduling**: Determines the order in which processes are executed by the CPU. The kernel uses scheduling algorithms to maximize efficiency and ensure fairness.
2. **Process Creation and Termination**: Manages the lifecycle of processes, including their initialization and cleanup after completion.
3. **Context Switching**: Saves and restores the state of processes during multitasking, allowing the CPU to switch between processes seamlessly.
4. **Inter-Process Communication (IPC)**: Facilitates communication and data exchange between processes.
5. **Deadlock Handling**: Detects and resolves deadlocks to ensure system stability.
6. **Resource Allocation**: Allocates CPU time, memory, and other resources to processes based on priority and requirements.

### Process States

Processes typically transition through the following states:

1. **New**: The process is being created.
2. **Ready**: The process is ready to execute but waiting for CPU time.
3. **Running**: The process is actively executing on the CPU.
4. **Waiting**: The process is waiting for an event or resource.
5. **Terminated**: The process has completed execution.

### Importance of Process Management

- **Efficiency**: Ensures optimal use of CPU and system resources.
- **Multitasking**: Enables multiple processes to run concurrently.
- **System Stability**: Prevents resource conflicts and ensures smooth operation.
- **User Experience**: Provides a responsive and interactive system for users.

Process management is a cornerstone of operating system functionality, enabling the execution of multiple applications and services in a coordinated and efficient manner.

### How is the CPU able to execute multiple processes at once?

It actually doesn't. It executes processes one-by-one through something known as a time slice.

### **Time Slice**

A time slice is a very short interval of time that gets allocated to a process for CPU execution.

The CPU executes one process in milliseconds, then executes another process, then another. To the human eye, everything looks like it runs simultaneously. That's how fast the CPU works.

# Memory Management and Virtual Memory

## Virtual Memory

Virtual memory is a memory management technique that allows the operating system to use a portion of the storage drive as if it were RAM. This enables the system to handle larger workloads and run more applications than the physical RAM would otherwise allow.

### Key Features of Virtual Memory

1. **Paging**: Divides memory into fixed-size blocks called pages, which can be swapped between RAM and storage as needed.
2. **Segmentation**: Divides memory into variable-sized segments based on logical divisions, such as functions or modules.
3. **Swap Space**: A designated area on the storage drive used to temporarily store data that cannot fit into RAM.

### How Virtual Memory Works

1. When the system runs out of physical RAM, it moves less frequently used data to the swap space.
2. The operating system retrieves this data back into RAM when needed, ensuring seamless operation.
3. This process is managed by the memory manager in the kernel.

### Advantages of Virtual Memory

- **Increased Capacity**: Allows systems to run applications that require more memory than physically available.
- **Isolation**: Provides memory isolation between processes, enhancing security and stability.
- **Efficient Multitasking**: Enables multiple applications to run simultaneously without exhausting physical RAM.

### Disadvantages of Virtual Memory

- **Performance Overhead**: Accessing data from storage is slower than accessing it from RAM.
- **Disk Wear**: Frequent swapping can lead to wear and tear on storage devices, especially SSDs.
- **Complexity**: Requires additional management by the operating system.

### Importance of Virtual Memory

Virtual memory is essential for modern operating systems, enabling them to handle complex workloads and provide a smooth user experience even with limited physical memory resources.

# Interacting with the OS

## Graphical User Interface (GUI)

A **Graphical User Interface (GUI)** is a visual way of interacting with a computer system using graphical elements such as windows, icons, buttons, and menus, rather than text-based commands.

### Key Features of a GUI

1. **Windows**: Rectangular areas on the screen that display information or allow user interaction.
2. **Icons**: Small graphical representations of files, applications, or functions.
3. **Menus**: Lists of options or commands that users can select.
4. **Buttons**: Clickable elements that perform actions or commands.
5. **Pointer**: A movable cursor controlled by a mouse or touchpad for selecting and interacting with elements.

### Advantages of a GUI

- **User-Friendly**: Intuitive and easy to learn, especially for non-technical users.
- **Visual Feedback**: Provides immediate visual responses to user actions.
- **Multitasking**: Allows users to work with multiple applications simultaneously using windows.
- **Accessibility**: Supports touchscreens, voice commands, and other input methods for diverse user needs.

### Disadvantages of a GUI

- **Resource-Intensive**: Requires more memory and processing power compared to text-based interfaces.
- **Complexity**: Can be overwhelming for users who prefer simplicity or need to perform advanced tasks.
- **Limited Control**: May not provide the same level of control as a Command-Line Interface (CLI) for certain operations.

### Examples of GUI-Based Operating Systems

- **Windows**: Known for its Start menu, taskbar, and desktop environment.
- **macOS**: Features the Dock, Finder, and Mission Control for navigation.
- **Linux (with Desktop Environments)**: Offers GUIs like GNOME, KDE Plasma, and XFCE.
- **Android and iOS**: Mobile operating systems with touch-based GUIs.

### Importance of GUIs

GUIs have revolutionized how users interact with computers, making technology accessible to a broader audience. They provide a visual and interactive experience, enabling users to perform tasks efficiently without needing to memorize commands.

# Logs

Logs are records of events, activities, or messages generated by the operating system, applications, or hardware components. They provide valuable insights into system behavior, performance, and potential issues.

### Types of Logs

1. **System Logs**: Contain information about the operating system's activities, such as boot processes, hardware events, and system errors.
2. **Application Logs**: Record events and messages generated by software applications, such as errors, warnings, or user actions.
3. **Security Logs**: Track security-related events, such as login attempts, access control changes, and potential breaches.
4. **Audit Logs**: Provide a detailed record of user activities and system changes for compliance and troubleshooting.
5. **Event Logs**: General logs that capture significant events occurring within the system or applications.

### Importance of Logs

- **Troubleshooting**: Help identify and resolve issues by providing detailed error messages and context.
- **Performance Monitoring**: Enable tracking of system and application performance over time.
- **Security**: Assist in detecting unauthorized access, suspicious activities, or potential vulnerabilities.
- **Compliance**: Provide evidence for audits and regulatory requirements.
- **System Analysis**: Offer insights into system behavior and usage patterns.

### Log Management

1. **Log Collection**: Gather logs from various sources, such as system files, applications, and network devices.
2. **Log Storage**: Store logs securely, ensuring they are accessible for analysis and auditing.
3. **Log Analysis**: Use tools or scripts to analyze logs for patterns, anomalies, or specific events.
4. **Log Rotation**: Manage log file sizes by archiving or deleting old logs to free up storage space.
5. **Log Monitoring**: Continuously monitor logs for real-time alerts and notifications.

### Common Log Locations

- **Linux**: Logs are typically stored in the `/var/log` directory (e.g., `syslog`, `auth.log`, `dmesg`).
- **Windows**: Logs can be accessed via the Event Viewer (e.g., Application, Security, System logs).
- **macOS**: Logs are available through the Console app or in `/var/log`.

### Tools for Log Management

- **Log Analysis Tools**: Splunk, ELK Stack (Elasticsearch, Logstash, Kibana), Graylog.
- **Monitoring Tools**: Nagios, Prometheus, Datadog.
- **Command-Line Utilities**: `grep`, `tail`, `less`, `journalctl`.

Logs are essential for maintaining system health, ensuring security, and diagnosing issues. Proper log management practices are critical for effective system administration and incident response.## Logs

# Booting up a system

Here's a rundown of the boot process.
First, the computer is powered on. The BIOS/UEFI is a low-level software that initializes our computer's hardware to make sure everything is good to go.
Next, the bios UEFI runs a process called the power-on self-test, or post. The post performs a series of diagnostic tests to make sure that the computer is in proper working order.
Next, depending on the bios or UEFI configuration of boot device will be selected. Devices that are attached to our system, like hard drives, USB drives, CD drives, etc, are configured in a certain boot order. The devices will be checked in this order and the computer will search for what's known as a bootloader.
The bootloader is a small program that loads the operating system. Once our computer finds a bootloader on a device in the listed order, it will start to execute this program. This will then start to load a larger and more complex program and eventually loads our operating system.
Once the bootloader loads up our operating system, our kernel gets loaded. The kernel controls access to our computer's resources. It also loads up drivers and more so that our hardware can talk to our software.
Next, essential system processes and user space items are launched. These include processes like user login, spinning up a desktop environment, and more which basically allows us to interact with our system.

# Virtual Machine

A virtual machine is just a copy of a real machine.
