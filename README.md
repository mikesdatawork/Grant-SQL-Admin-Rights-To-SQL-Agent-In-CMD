![MIKES DATA WORK GIT REPO](https://raw.githubusercontent.com/mikesdatawork/images/master/git_mikes_data_work_banner_01.png "Mikes Data Work")        

# Grant SQL Admin Rights To SQL Agent In CMD
**Post Date: November 9, 2016**        



## Contents    
- [About Process](##About-Process)  
- [Build Info](#Build-Info)  
- [Author](#Author)  
- [License](#License)       

## About-Process

<p>If you're creating a job process under the SQL Server Agent and you're expecting to run an OS based command from xp_cmdshell you may run into an error where the SQL Service Account doesn't have the following 3 rights.
  
1. The right to back up files and directories.
2. The right to manage auditing and the security log.
3. The right to debug programs.

In most cases these rights are automatically assumed if your account has Administrator rights in the OS, and you're logged on directly but instead of using an SQL process to run the CMD command; you're simply using Command Prompt, and you've already explicitly opened it using 'Run as Administrator'.

In security architecture these privileges are knows as the following:
SeBackupPrivilege
SeDebugPrivilege
SeSecurityPrivilege</p>

These are fairly easy to add if you've got rights to the local security policies, and here's how to add them.
Go to Startà Run, and run secpol.msc

![Start Run SecPol Msc]( https://mikesdatawork.files.wordpress.com/2016/11/image0015.png "Local Security Policy")
 
Expand 'Local Policies', and select 'User Rights Assignments'.

![Modify Configs]( https://mikesdatawork.files.wordpress.com/2016/11/image0023.png "Modify Security Policy")
 
You'll need to click each one of these and ensure the SQL Service Accounts have been added to them. If you're creating the Agent Jobs to run under another account that isn't a service account then you'll need to add it directly as well. 


[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Build-Info

| Build Quality | Build History |
|--|--|
|<table><tr><td>[![Build-Status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg?style=flat-square)](#)</td></tr><tr><td>[![Coverage](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?style=flat-square)](#)</td></tr><tr><td>[![Nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg?style=flat-square)](#)</td></tr></table>|<table><tr><td>[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](#)</td></tr></table>|

## Author

[![Gist](https://img.shields.io/badge/Gist-MikesDataWork-<COLOR>.svg)](https://gist.github.com/mikesdatawork)
[![Twitter](https://img.shields.io/badge/Twitter-MikesDataWork-<COLOR>.svg)](https://twitter.com/mikesdatawork)
[![Wordpress](https://img.shields.io/badge/Wordpress-MikesDataWork-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)


## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Mikes Data Work](https://raw.githubusercontent.com/mikesdatawork/images/master/git_mikes_data_work_banner_02.png "Mikes Data Work")

