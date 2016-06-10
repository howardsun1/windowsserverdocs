---
title: Avoid using VHD-format differencing virtual hard disks on virtual machines that run server workloads in a production environment
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: 
  - hyper-v
  - techgroup-compute
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 272de33d-2708-4679-8564-ee28848a2839
author: KBDAzure
---
# Avoid using VHD-format differencing virtual hard disks on virtual machines that run server workloads in a production environment
\[This information is preliminary and subject to change.\]  
  
For more information about best practices and scans, see [Run Best Practices Analyzer Scans and Manage Scan Results](http://go.microsoft.com/fwlink/p/?LinkID=223177).  
  
|||  
|-|-|  
|**Operating System**|[!INCLUDE[winthreshold_server_2](includes/winthreshold_server_2_md.md)] |  
|**Product\/Feature**|Hyper\-V|  
|**Severity**|Warning|  
|**Category**|Configuration|  
  
In the following sections, italics indicates UI text that appears in the Best Practices Analyzer tool for this issue.  
  
## **Issue**  
*One or more virtual machines use VHD\-format differencing virtual hard disks.*  
  
## **Impact**  
*VHD\-format differencing virtual hard disks could experience consistency issues if a power failure occurs. Consistency issues can happen if the physical disk performs an incomplete or incorrect update to a sector in a .vhd file that is being modified when a power failure occurs. This affects the following virtual machines:*  
  
\<list of virtual machines>  
  
## **Resolution**  
*Shut down the virtual machine and convert the chain of VHD\-format differencing virtual hard disks to the VHDX format or merge the chain to a fixed virtual hard disk. \(The VHDX format has reliability mechanisms that help protect the disk from corruptions due to power failures.\) However, do not convert the virtual hard disk if it is likely to be attached to an earlier release of Windows at some point. Windows releases earlier than [!INCLUDE[win8_server_2](includes/win8_server_2_md.md)] do not support the VHDX format.*  
  
