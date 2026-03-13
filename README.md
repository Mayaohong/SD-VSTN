# Traffic Data Repository

## Overview

This repository contains the SU1 (SeoulUrban1) and SU2 (SeoulUrban2) traffic datasets used. These datasets are constructed following the same method as LibCity's atomic files structure, ensuring compatibility with existing traffic prediction frameworks.

## Data Construction

The SU1 and SU2 datasets are constructed using the same methodology as [LibCity](https://github.com/LibCity)'s atomic files structure. This ensures consistency with the widely adopted data format in traffic prediction research, allowing for seamless integration with existing models and tools.

## Atomic Files Explanation

Each dataset (SU1 and SU2) consists of the following atomic files:

### 1. `.geo` File

The `.geo` file contains geographical information about the road segments. It includes:

- `geo_id`: Unique identifier for each road segment
- `type`: Type of geographical entity (LineString for road segments)
- `coordinates`: Spatial coordinates defining the geometry of each road segment

Example structure:
```
geo_id,type,coordinates
0,LineString,[[]]
1,LineString,[[]]
...
```

### 2. `.rel` File

The `.rel` file defines relationships between geographical entities. It includes:

- `rel_id`: Unique identifier for each relationship
- `type`: Type of relationship (e.g., geo for spatial relationships)
- `origin_id`: ID of the origin road segment
- `destination_id`: ID of the destination road segment
- `cost`: Weight of the relationship (e.g., distance or travel time)

### 3. `.dyna` File

The `.dyna` file contains dynamic traffic data over time. It includes:

- `dyna_id`: Unique identifier for each dynamic record
- `type`: Type of dynamic data (e.g., state for traffic state)
- `time`: Timestamp of the record
- `entity_id`: ID of the road segment (matching geo_id)
- `traffic_speed`: Traffic speed value at the given time

### 4. `config.json` File

The `config.json` file provides configuration information for the dataset, including:

- `geo`: Configuration for geographical data
- `rel`: Configuration for relationship data
- `dyna`: Configuration for dynamic data
- `info`: General information about the dataset (data columns, time intervals, etc.)

## Dataset Statistics

### SU1 (SeoulUrban1)
- Number of road segments: 560
- Time intervals: 300 seconds (5 minutes)
- Temporal coverage: [Specify time period if available]
- Data features: Traffic speed

### SU2 (SeoulUrban2)
- Number of road segments: [Specify if different from SU1]
- Time intervals: 300 seconds (5 minutes)
- Temporal coverage: [Specify time period if available]
- Data features: Traffic speed

## Download Link

The datasets can be downloaded from Baidu Netdisk:

- **Link**: [https://pan.baidu.com/s/1NE1BUylsjKRssFS0OmnUyQ?pwd=myh8](https://pan.baidu.com/s/1NE1BUylsjKRssFS0OmnUyQ?pwd=myh8)
- **Extraction Code**: myh8

## Usage

To use these datasets with LibCity or compatible frameworks:

1. Download the datasets using the provided link
2. Extract the files to the `raw_data` directory
3. Ensure the directory structure matches the existing format
4. Configure your model to use the appropriate dataset name (e.g., "SeoulUrban1" or "SeoulUrban2")

## Related Work

The data structure follows the [LibCity](https://github.com/LibCity) atomic files format, which is described in detail in the LibCity documentation. This format is designed to provide a standardized way to represent traffic data for machine learning models.

## Contact

For questions about the datasets, please contact yhma95@qq.com.
