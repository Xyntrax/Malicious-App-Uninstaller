# Malicious App Uninstaller Portable (MAU)

MAU is a Windows tool designed to simplify the removal of malicious applications installed by malware.

## Download

[Download MAU](https://github.com/Xyntrax/Malicious-App-Uninstaller/raw/main/Malicious_App_Uninstaller.zip)

This is a test build and is not intended for actual malware-removal cases yet.

## What MAU Does

MAU uses an application's ProductCode to analyze its registered installation footprint and identify associated traces, including files, registry entries, installer data, services, and other related artifacts.

Instead of invoking the application's registered uninstall routine, MAU allows the identified traces to be removed directly.

## Why MAU Was Created

Malware remediation using FRST and custom inline PowerShell/CMD commands in the Fixlist can require an additional step after the active infection has been addressed to remove the malicious application it installed. MAU was created to simplify this part of the remediation process and eliminate the need to create a second Fixlist for the removal of the malicious application.

Unlike general-purpose uninstallers such as Revo Uninstaller, Geek Uninstaller, and BCUninstaller, MAU avoids invoking the application's registered uninstaller. For malicious applications, running the registered uninstaller can trigger the malicious installer and potentially reinfect the system.

For PUPs and other unwanted or legitimate software, general-purpose uninstallers remain better suited.

## Workflow

MAU is intended to be used alongside FRST:

1. Address the active infection with the FRST Fixlist.
2. Identify the malicious application's ProductCode, if the malware installed one.
3. Select the application in MAU or enter the ProductCode manually.
4. MAU will scan and display the discovered traces.
5. Select the traces to remove, or use **Select All**.
6. Delete the selected traces.
7. Restart Windows if MAU schedules files for removal at restart.
8. Generate new FRST logs for a final post-removal check.
