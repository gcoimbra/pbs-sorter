# pbs-sorter
Get the most of OpenPBS with a simple script by adding memory or cpu requirements and sort by highest node with available memory.

OpenPBS can requests from the user the maximum number of CPU and Memory a job can use, but sometimes we know our jobs will scale well and the higher the available memory or cpu the faster it will finish. So, instead of submitting a job to OpenPBS with a somewhat arbitrary number for mem and cpu requirements (and hope the job doesn't wait too long in a queue or work too slow when it could go faster as the cluster is not very busy). Instead, we can get automatically the number of cpu and memory available in the cluster right now and submit the job with the highest possible and according to some mininum requirements.

## Requirements
Python 3.9+ should work

Pandas

Pandas isn't necessary but it's easily available everywhere and really easy to work with.

## Usage

## Command line usage example

The script will raise error if cpu or memory requirements aren't met.


Set a minimum requirements of 8 CPU cores and 16 GB of memory and sort by CPU. 
$ python3 automaticMemCPUPBS.py --sort cpu
CPUs available 19
GB available 1

The script will filter down or unresponsive nodes and will return the number of CPU and Memory in a node that is free (not used by other jobs) according to the requirements. The cpu and memory requirements are optional but the sorting argument is obligatory. I will sort the nodes that meet the requirement and have the highest amount of cpu cores or memory depending on the sort parameter.
