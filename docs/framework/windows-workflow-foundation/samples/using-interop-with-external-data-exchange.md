---
title: Verwenden von Interop mit dem External Data Exchange-Dienst
ms.date: 03/30/2017
ms.assetid: 96f6fe26-5305-494f-9119-7748e0c4b3fa
ms.openlocfilehash: 534321e5b5568e0dd0988333dc98ccc18ff33df8
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2018
ms.locfileid: "44508295"
---
# <a name="using-interop-with-external-data-exchange"></a>Verwenden von Interop mit dem External Data Exchange-Dienst
Die <xref:System.Activities.Statements.Interop> Aktivität kann zum Ausführen von Aktivitäten von Windows Workflow Foundation (WF) in [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] und [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF3) sowie Workflows aus Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF4). In diesem Beispiel wird veranschaulicht, wie ein WF3-Workflow, der <xref:System.Workflow.Activities.ExternalDataExchangeService> (sowie entsprechende benutzerdefinierte Aktivitäten zum Aufrufen von Methoden und Behandeln von Ereignissen) verwendet, mit der <xref:System.Activities.Statements.Interop>-Aktivität in einem WF4-Workflowdienst konfiguriert und ausgeführt werden kann.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\ExternalDataExchange`  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Datei ExternalDataExchange.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Drücken Sie STRG+UMSCHALT+B, um das Beispiel zu erstellen.  
  
3.  Drücken Sie F5, um das Beispiel auszuführen.
