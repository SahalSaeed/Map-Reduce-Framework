# MapReduce Framework in C++

A comprehensive implementation of the MapReduce paradigm in C++ that simulates distributed data processing on a single machine using parallel processing and core operating system concepts.

## 🚀 Overview

This project demonstrates a complete MapReduce framework that efficiently processes large-scale data through parallel computation. The implementation showcases essential distributed systems concepts including concurrent computing, synchronization, and the three-phase MapReduce workflow.

## 📋 Table of Contents

- [Features](#features)
- [Architecture](#architecture)
- [Installation](#installation)
- [Usage](#usage)
- [Example Workflow](#example-workflow)
- [Technical Implementation](#technical-implementation)
- [Configuration](#configuration)
- [Contributing](#contributing)
- [License](#license)

## ✨ Features

- **Parallel Processing**: Multi-threaded execution for optimal performance
- **Key-Value Pair Management**: Efficient intermediate data handling
- **Synchronization**: Thread-safe operations with proper synchronization mechanisms
- **Memory Management**: Optimized resource allocation and cleanup
- **Configurable Test Cases**: Multiple test scenarios included
- **Cross-Platform Compatibility**: Standard C++ implementation

## 🏗️ Architecture

The framework implements the classic MapReduce paradigm through three distinct phases:

### 1. Map Phase
- Processes input data in parallel chunks
- Each chunk handled by independent map functions
- Outputs intermediate key-value pairs
- Utilizes multithreading for performance optimization

### 2. Shuffle Phase
- Groups intermediate key-value pairs by key
- Ensures all occurrences of a key are collected together
- Prepares data for efficient reduce processing
- Critical for maintaining data locality

### 3. Reduce Phase
- Processes grouped key-value pairs
- Performs aggregation and computation on values
- Produces final output results
- Handles multiple keys in parallel

## 📦 Installation

### Prerequisites
- C++ compiler (GCC 4.8+ or equivalent)
- Make utility
- POSIX-compliant system (for pthreads)

### Setup

```bash
# Clone the repository
git clone https://github.com/SahalSaeed/Map-Reduce-Framework.git

# Navigate to project directory
cd Map-Reduce-Framework

# Build the project
make

# Run the application
./main
```

## 🔧 Usage

### Basic Execution

```bash
# Compile the project
make

# Execute with default test case
./main
```

### Custom Test Cases

The framework includes multiple test scenarios. To switch between test cases:

1. Open `main.cpp`
2. Modify line 26 to change the input file:
   ```cpp
   // Change from test1.txt to test2.txt or test3.txt
   string inputFile = "test2.txt";
   ```
3. Recompile and run

## 📊 Example Workflow

**Input Data:**
```
pizza burger pasta pasta pizza
```

**Map Phase Output:**
```
("pizza", 1), ("burger", 1), ("pasta", 1), ("pasta", 1), ("pizza", 1)
```

**Shuffle Phase Output:**
```
("pizza", [1, 1]), ("burger", [1]), ("pasta", [1, 1])
```

**Reduce Phase Output:**
```
("pizza", 2), ("burger", 1), ("pasta", 2)
```

## 🔧 Technical Implementation

### Core Technologies
- **Language**: C++
- **Threading**: POSIX Threads (pthreads)
- **I/O**: Standard File I/O operations
- **Synchronization**: Mutexes and condition variables

### Key Concepts
- **Multithreading**: Parallel processing of data chunks
- **Synchronization**: Race condition prevention and resource management
- **Memory Management**: Efficient allocation and deallocation strategies
- **Load Distribution**: Balanced workload across available threads

### Performance Considerations
- Thread pool management for optimal resource utilization
- Efficient data structures for key-value pair storage
- Minimized memory footprint during processing
- Scalable design for varying input sizes

## ⚙️ Configuration

### Test Files
- `test1.txt`: Basic word counting example
- `test2.txt`: Extended vocabulary test
- `test3.txt`: Large-scale data processing scenario

### Customization Options
- Modify thread count in the source code
- Adjust buffer sizes for different data volumes
- Configure output formatting preferences

## 🚀 Future Enhancements

- **Dynamic Load Balancing**: Intelligent work distribution
- **Distributed Processing**: Multi-machine cluster support
- **Fault Tolerance**: Error recovery and failover mechanisms
- **Performance Monitoring**: Real-time metrics and profiling
- **Configuration Management**: Runtime parameter adjustment

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Development Guidelines
- Follow existing code style and conventions
- Add unit tests for new functionality
- Update documentation for any changes
- Ensure thread safety in concurrent operations

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## 📞 Support

For questions, issues, or suggestions:
- Open an issue on GitHub
- Check existing documentation
- Review the example implementations

---

**Note**: This implementation serves as an educational demonstration of MapReduce concepts and parallel processing techniques. For production use, consider additional optimizations and error handling mechanisms.