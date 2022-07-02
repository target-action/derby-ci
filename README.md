# Derby CI
Just to compare speed of different CI options (available without billing) for Apple developers, using quite popular for estimating local build times [XcodeBenchmark](https://github.com/devMEremenko/XcodeBenchmark) as a submodule.
For now I just setup simple script step on different CI providers, and manually update the readme with results. To be automated in future.

# CI Providers (from fastest to slowest)

## Xcode 13.0 or above

|       Provider                |           CPU           | RAM | Xcode |  macOS  | Time(sec) |
|:-----------------------------:|:-----------------------:|:---:|:-----:|:-------:|:---------:|
| Bitrise M1 Elite XL           |      M1 XXX 8-core      |  12 | 13.4.1| 12.3.1  |    143    |
| Bitrise (Elite Gen2)          |     3.19 GHz 8-core     |  35 | 13.4.1| 12.2.1  |    313    |
| Bitrise (Standard)            |     3.19 GHz 4-core     |  19 | 13.4.1| 12.2.1  |    407    |
| Semaphore CI (a1-standard-4)  |     2.58 GHz 4-core     |   8 | 12.5.1| 11.5.1  |    584    |
| Codemagic (mac_mini)          |     2.19 GHz 4-core     |   8 | 13.4.1| 12.4    |    679    |
| Github Actions                |     3.33 GHz 3-core     |  14 | 13.2.1| 11.6.6  |    714    |


## Notes
More and more CI providers add M1 machines to their stack, although in most cases they require billing setup, so far I've found only Bitrise M1, which runs pretty fast (e.g. comparing to XcodeBenchmark results, close to MacBook Pro 13" 2020 with 130 sec).

## Detailed Log
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

### Semaphore CI (a1-standard-4)
#### Build Time: 584 sec

- System Version: 11.5.1
- Xcode 12.5.1
- Hardware Overview
    - Model Name: MacBook Air
    - Model Identifier: MacBookAir7,1
    - Processor Name: Unknown
    - Processor Speed: 2.58 GHz
    - Total Number of Cores: 4
    - Number of Processors: 4
    - Memory: 8 GB

### Codemagic (mac_mini)
#### Build Time: 679 sec

- System Version: 12.4
- Xcode 13.4.1
- Hardware Overview
    - Model Name: Mac
    - Model Identifier: VMware7,1
    - Processor Name: Unknown
    - Processor Speed: 2.19 GHz
    - Total Number of Cores: 4
    - Number of Processors: 4
    - Memory: 8 GB

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
