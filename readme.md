# Week 2 Scripting Like A Developer

The code found in this repository is to help you learn how to script like a developer.

## WIP
The code found in 'Week-2-Scripting-Like-A-Developer' is currently a Work In Progress (WIP) and the readme will be updated when ready

## PowerShell Code
The Powershell code found in 'Week-2-Scripting-Like-A-Developer' is for anyone that wants to create a Resource Group in Azure

## How to Use The PowerShell Code
The 'New-RespurceGroup' function is found under the 'PowerShell' directory and can be used as a reusable function. A user has the ability to pass in parametersat runtime to ensure they can re-use the script at any point for any environment.

## Python Code
The Python code found in 'Week-2-Scripting-Like-A-Developer' is for anyone that wants to create an S3 bucket in AWS

## How to Use The Python Code
The 's3bucket.py' script is designed to be re-used at any point for any environment. There are no hard-coded values.

## Examples
'''Pwsh
function New-ResourceGroup {
    [cmdletbinding(SupportsShouldProcess)]

    param (
        [parameter(Mandatory)]
        [string]$rgName,

        [parameter(Mandatory)]
        [string]$location
    )

    $params = @{
        'Name' = $rgName
        'Location' = $location
    }
    if ($pscmdlet.ShouldProcees('location')) {
        New-AzResourceGroup @params
    }
}

New-ResourceGroup -rgName 'cloudskills2173' -location 'eastus2'
'''

'''Python
import sys
import boto3


try:
    def main():
        create_s3bucket(bucket_name)

except Exception as e:
    print (e)

def create_s3bucket(bucket_name):
    s3_bucket=boto3.client(
        's3'
    )

    bucket = s3_bucket.create_bucket(
        Bucket=bucket_name,
        ACL='private',
    )

    print(bucket)

bucket_name = sys.argv[1]

if __name__ == '__main__':
    main()

python test2.py 'cloudskillss3bucket'
'''

## Testing
Both the PowerShell and Python testing codes have unit tests available to ensure the desired outcomes, including values and types, are accurate.

The test cane be found in the 'PowerShell' and 'Python' directories.


## Contributers
1. Emad Hirsi