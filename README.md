# File-Integrity-Monitoring-Tool [FIM Tool]

The provided PowerShell script is a file integrity monitoring tool that allows users to either collect a new baseline of file hashes or monitor files against a saved baseline. 

### Project Summary

1. **Hash Calculation**: Uses SHA512 to compute file hashes.
2. **Baseline Management**:
   - Option to create a new baseline by hashing all files in a specified directory and saving these hashes to `baseline.txt`.
   - Option to monitor files continuously, comparing their current hashes to the saved baseline.
3. **Monitoring**: Alerts the user if files are added, modified, or deleted based on the comparison to the baseline hashes.

### Detailed Analysis

1. **Function `Calculate-File-Hash`**:
   - Takes a file path as input.
   - Computes and returns the SHA512 hash of the file.

2. **Function `Erase-Baseline-If-Already-Exists`**:
   - Checks if `baseline.txt` exists.
   - Deletes `baseline.txt` if it is present.

3. **Main Script**:
   - Prompts the user to choose between creating a new baseline or monitoring files.
   - If creating a new baseline:
     - Deletes any existing `baseline.txt`.
     - Computes and stores the hashes of all files in the `.\Files` directory to `baseline.txt`.
   - If monitoring files:
     - Loads the saved file hashes from `baseline.txt` into a dictionary.
     - Continuously monitors the `.\Files` directory, checking for file additions, changes, or deletions.
     - Alerts the user if:
       - A new file is created.
       - An existing file is modified.
       - An existing file is deleted.

### Use Case

This script is useful for environments where maintaining file integrity is crucial, such as in cybersecurity, data integrity monitoring, and compliance auditing. It ensures that any unauthorized changes to critical files are detected promptly, enhancing the security and reliability of the system.
