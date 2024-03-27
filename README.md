![Static Badge](https://img.shields.io/badge/python-3%2E7_%7C_3%2E8_%7C_3%2E9_%7C_3%2E10-blue)
![Static Badge](https://img.shields.io/badge/license-Apache_2%2E0-blue)
![PyPI - Version](https://img.shields.io/pypi/v/ibm-cos-sdk?label=ibm-cos-sdk)



# IBM Cloud Object Storage - Unarchive

This is a Python script to restore archived object in Object Storage.

***Note:***
Only objects with Storage Class **ACCELERATED** or **GLACIER** are considered.

## Installing

Before running the script, you must install ibm-cos-sdk (IBM COS SDK for Python). You can install with:

```shell
pip install -r requirements.txt
```

## Running

To run the script:

```shell
chmod +x unarchive.py
./unarchive.py --apikey APIKEY -b BUCKET --crn CRN -d DAYS
```

## Usage

```shell
usage: unarchive.py [-h] --apikey APIKEY -b BUCKET [--prefix PREFIX] [--continue-after AFTER] --crn CRN [-r REGION] -d DAYS [-s SIZE] [-t THREADS] [-v]

A python script to restore archived object in Object Storage.

options:
  -h, --help                              show this help message and exit
  --apikey APIKEY                         Required) API Key string
  -b BUCKET, --bucket BUCKET              (Required) The name of the bucket
  --prefix PREFIX                         Limits the response to keys that begin with the specified prefix. Page number calculation uses a slower method.
  --resume                                Continue a restore after the last object in the log.
  --crn CRN                               (Required) COS service id (CRN)
  -r REGION, --region REGION              COS Region. Default region is eu-de
  --endpoint-type {private,public,direct} COS Endpoint Type. Default is public. It could be public, private or direct
  -d DAYS, --days DAYS                    (Required) Specified the lifetime of the temporarily restored object
  -s SIZE, --size SIZE                    Restricts the number of objects to retrieve. Default and maximum is 1000
  -t THREADS, --threads THREADS           Number of parallel threads. Must be less than SIZE. Default is 10
  -v, --verbose                           Enable verbose logs
  ```
