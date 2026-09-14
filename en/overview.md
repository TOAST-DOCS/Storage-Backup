<!-- machine_translated: true -->

<!-- pre-align:aligned sig=755f913dbd4d -->

<a id="storage-backup-overview"></a>
## Storage > Backup > Overview { #storage-backup-overview }

Backup is a service that makes copies and keeps them safely to prepare for data loss due to security threats, user's operational mistakes, storage device failure, natural disasters, and so on. You can also restore data using the backup copy.

NHN Cloud Backup service uses both full and incremental backup methods. Initially, the service performs backup of all data in the path registered by the user. Afterwards, only incremental backups are performed using variable-length deduplication technology, which can minimize backup data by removing duplicates. This shortens backup times and reduces network usage. Data is encrypted and transferred securely to backup storage.

NHN Cloud Backup service provides a web console environment where you can easily register backup policies, view backup history, and request restoration. Backup results are collected daily and reported to the user's email.

<a id="service-features"></a>
## Service Features { #service-features }
* Supports various operating systems.
* Optimized for virtualization environment.
* Performs backup without interrupting the service.
* Provides a user-defined backup policy that allows you to set the backup cycle, backup time, and retention cycle.

<a id="backup-cycle"></a>
### Backup Cycle { #backup-cycle }
You can choose between 1-day interval and 7-day interval.

<a id="backup-time"></a>
### Backup Time { #backup-time }
You can select a backup start time by the hour. It is recommended to select the time when the number of file change is minimal and the server is idle. Actual backup start time may vary by up to 1 hour, depending on the situation.

<a id="retention-cycle"></a>
### Retention Cycle { #retention-cycle }
You can select a retention cycle of 7 days, 14 days, 21 days, 30 days, 6 months (180 days), 1 year (365 days), 3 years (1095 days), or 5 years (1825 days).

<a id="view-results"></a>
### View Results { #view-results }
Users can view backup results on the web console within 30 minutes from the backup completion time. If the backup fails, the details of failure are reported to the user's email. If the backup is not performed up to 3 hours, it is logged as a failure.

Backup result emails are sent at 10:30 AM after information is collected at 10:00 AM daily. Even if a backup schedule starts before 10:00 AM, if it completes after 10:00 AM, the backup result email may not be sent on that day.

<a id="supported-operating-systems"></a>
## Supported Operating Systems { #supported-operating-systems }
NHN Cloud supports the following operating systems:

| OS | Hardware Architecture | Supported Version | Supported Configuration |
| --- | --- | --- | --- |
| CentOS | x64 | 7.8 | ext2, ext3, ext4, xfs |
| Ubuntu | x64 | 18.04 LTS<br/>20.04 LTS | ext2, ext3, ext4 |
| Debian | x64 | 9, 10 | ext2, ext3, ext4 |
| Rocky | x64 | 8.5 | xfs |
| Windows Server | x64 | 2012 R2 STD<br/>2016 STD<br/>2019 STD | NTFS |

<a id="restoration"></a>
## Restoration { #restoration }
Select one of the backup results from the original server to restore. You can restore the entire backup or select a specific path.
The restore target server can be selected from among the servers with the backup agent installed, and must be a server with the same OS family (Linux or Windows) as the restore source server.
You can specify the save path you want. If the entered path does not exist, it will be automatically created and then restored.

<a id="charges"></a>
## Charges { #charges }
When a server is registered, a basic monthly fee is charged. Additional fees apply based on the number of registered servers, storage usage, and the size of restored data. The default specification for the monthly subscription includes two servers and 100 GB of storage usage.

<a id="reference"></a>
## Reference { #reference }
<a id="backup-software"></a>
### Backup Software { #backup-software }
DELL EMC AVAMAR

<a id="backup-program-installation-location"></a>
### Backup Program Installation Location { #backup-program-installation-location }
* Linux : /usr/local/avamar
* Windows : C:\Program Files\avs

<a id="backup-program-daemon-process-information"></a>
### Backup Program Daemon (Process) Information { #backup-program-daemon-process-information }
* Linux : /usr/local/avamar/bin/avagent.bin
* Windows : Avamar Backup Client
