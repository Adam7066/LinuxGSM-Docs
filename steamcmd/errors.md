---
description: Common
---

# Errors

## SteamCMD

SteamCMD can sometimes output errors when something goes wrong. Sadly Valve have never released an official list of what the error messages mean. Because of this, a lot of guess work has been needed to figure it out. This page will highlight what we already know and info on researching what the error might mean in the hope that you can contribute to understanding SteamCMD errors.

SteamCMD uses hexadecimal numbers to give its current "state". Every time SteamCMD does something it changes its state. When SteamCMD fails it will output its has hexadecimal state, for example `0x202`.

## Codes

### Error 0x202

Not enough disk space.

```text
Error! App '<appid_number>' state is 0x202 after update job.
```

|  |  |
| :--- | :--- |
| Reason | Not enough disk quota |
| Hex | 0x202 |
| Decimal/StateFlags | 514 |

{% file src="../.gitbook/assets/content\_log.txt" caption="content\_log.txt 0x202 example" %}

### Error 0x206

{% hint style="info" %}
Unknown error, if you have any details please let us know
{% endhint %}

```text
Error! App '<appid_number>' state is 0x206 after update job.
```

|  |  |
| :--- | :--- |
| Reason |  |
| Hex | 0x206 |
| Decimal/StateFlags | 518 |

{% hint style="info" %}
Missing content\_log.txt if you have experienced this error and have a log it please let us know.
{% endhint %}

### Error 0x402

Connection issue with steam, you will need to wait for the steam servers to recover.

```text
Error! State is 0x402 after update job.
```

|  |  |
| :--- | :--- |
| Reason |  |
| Hex | 0x402 |
| Decimal/StateFlags | 1026 |

{% hint style="info" %}
Missing content\_log.txt if you have experienced this error and have a log it please let us know.
{% endhint %}

### Error 0x602

{% hint style="info" %}
Unknown error, if you have any details please let us know
{% endhint %}

```text
Error! State is 0x602 after update job.
```

|  |  |
| :--- | :--- |
| Reason |  |
| Hex | 0x602 |
| Decimal/StateFlags | 1538 |

{% hint style="info" %}
Missing content\_log.txt if you have experienced this error and have a log it please let us know.
{% endhint %}

### Error 0x606

{% hint style="info" %}
Unknown error, if you have any details please let us know
{% endhint %}

```text
Error! App '<appid_number>' state is 0x606 after update job.
```

|  |  |
| :--- | :--- |
| Reason |  |
| Hex | 0x606 |
| Decimal/StateFlags | 1542 |

{% hint style="info" %}
Missing content\_log.txt if you have experienced this error and have a log it please let us know.
{% endhint %}

### Error 0x2

```text
Error! App '<appid_number>' state is is 0x2 after update job.
```

|  |  |
| :--- | :--- |
| Reason |  |
| Hex | 0x2 |
| Decimal/StateFlags | 2 |

{% hint style="info" %}
Missing content\_log.txt if you have it please let us know.
{% endhint %}

### 0x3

```text
Update state (0x3) reconfiguring, progress: 0.00 (0 / 0)
```

### 0x5

```text
Update state (0x5) validating, progress: 13.48 (1554089956 / 11530459441)
```

### 0x11

```text
Update state (0x11) preallocating, progress: 8.53 (983870089 / 11530459441)
```

### 0x61

```text
Update state (0x61) downloading, progress: 1.11 (127644881 / 11530459441)
```

### 0x101

```text
 Update state (0x101) committing, progress: 3.43 (395043827 / 11530459441)
```

## SteamCMD Logs

To get more info and output see the SteamCMD logs in `~/.steam/logs`. The most useful log is `content_log.txt` that will provide more information of errors. 

{% hint style="success" %}
If you have experienced an error we don't have logs for please can you provide them to us to assist in diagnosing the issue.
{% endhint %}

## SteamCMD Hex Codes

SteamCMD uses hex error codes such as `0x202` which can be converted in to decimal `514`. Using the table below you can work out that the status messages. By doing a calculation. Find the highest number below the state `512` which if the first error. Then take the number away from the total `514-512=2`  which gives you the last error. This can be done for any error

`514-512-2=0`

`512 StateUpdateRunning` , `2 StateUpdateRequired`

|  |  |
| :--- | :--- |
| StateInvalid | 0 |
| StateUninstalled | 1 |
| StateUpdateRequired | 2 |
| StateFullyInstalled | 4 |
| StateEncrypted | 8 |
| StateLocked | 16 |
| StateFilesMissing | 32 |
| StateAppRunning | 64 |
| StateFilesCorrupt | 128 |
| StateUpdateRunning | 256 |
| StateUpdateRunning | 512 |
| StateUpdateStarted | 1024 |
| StateUninstalling | 2048 |
| StateBackupRunning | 4096 |
| StateReconfiguring | 65536 |
| StateValidating | 131072 |
| StateAddingFiles | 262144 |
| StatePreallocating | 524288 |
| StateDownloading | 1048576 |
| StateStaging | 2097152 |
| StateCommitting | 4194304 |
| StateUpdateStopping | 8388608 |

This table is from 2015 and is probably out dated now but its the best we currently have.

[https://github.com/lutris/lutris/blob/master/docs/steam.rst](https://github.com/lutris/lutris/blob/master/docs/steam.rst)
