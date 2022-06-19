# Derby CI
Just to compare speed of different CI options for Apple developers, using quite popular for estimating local build times [XcodeBenchmark](https://github.com/devMEremenko/XcodeBenchmark) as a submodule.
For now I just setup simple script step on different CI providers, and manually update the readme with results. To be automated in future.

# CI Providers (from fastest to slowest)

### Bitrise (M1 Elite XL)
#### Build Time: 143 sec (18 cr)

- System Version: 12.3.1
- Xcode 13.4.1
- Hardware Overview
    - Model Name: Apple Virtual Machine 1
    - Model Identifier: VirtualMac2,1
    - Total Number of Cores: 8
    - Memory: 12 GB

### Bitrise (Elite Gen2)
#### Build Time: 313 sec (24 cr)

- System Version: 12.2.1
- Xcode 13.4.1
- Hardware Overview
    - Model Name: Mac mini
    - Model Identifier: Macmini6,2
    - Processor Name: Unknown
    - Processor Speed: 3.19 GHz
    - Total Number of Cores: 8
    - L2 Cache (per Core): 256 KB
    - L3 Cache: 12 MB
    - Number of Processors: 1
    - Memory: 35 GB

### Bitrise (Standard Machine)
#### Build Time: 407 sec (16 cr)

- System Version: 12.2.1
- Xcode 13.4.1
- Hardware Overview
    - Model Name: Mac mini
    - Model Identifier: Macmini6,2
    - Processor Name: Unknown
    - Processor Speed: 3.19 GHz
    - Total Number of Cores: 4
    - L2 Cache (per Core): 256 KB
    - L3 Cache: 12 MB
    - Number of Processors: 1
    - Memory: 19 GB

### Github Actions
#### Build Time: 714 sec

- System Version: 11.6.6
- Xcode 13.2.1
- Hardware Overview
  - Model Name: Mac
  - Model Identifier: VMware7,1
  - Processor Name: Unknown
  - Processor Speed: 3.33 GHz
  - Total Number of Cores: 3
  - L2 Cache (per Core): 256 KB
  - L3 Cache: 12 MB
  - Number of Processors: 1
  - Memory: 14 GB
