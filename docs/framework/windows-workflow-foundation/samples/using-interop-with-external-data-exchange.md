---
title: Verwenden von Interop mit dem External Data Exchange-Dienst
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96f6fe26-5305-494f-9119-7748e0c4b3fa
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a17e4a51648facbc17e6af31f65360a3414a5c15
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="using-interop-with-external-data-exchange"></a>Verwenden von Interop mit dem External Data Exchange-Dienst
Mit der <xref:System.Activities.Statements.Interop>-Aktivität können Aktivitäten aus [!INCLUDE[wf](../../../../includes/wf-md.md)] in [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] und [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF3) sowie Workflows aus [!INCLUDE[wf2](../../../../includes/wf2-md.md)] in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF4) ausgeführt werden. In diesem Beispiel wird veranschaulicht, wie ein WF3-Workflow, der <xref:System.Workflow.Activities.ExternalDataExchangeService> (sowie entsprechende benutzerdefinierte Aktivitäten zum Aufrufen von Methoden und Behandeln von Ereignissen) verwendet, mit der <xref:System.Activities.Statements.Interop>-Aktivität in einem WF4-Workflowdienst konfiguriert und ausgeführt werden kann.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\ExternalDataExchange`  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Datei ExternalDataExchange.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Drücken Sie STRG+UMSCHALT+B, um das Beispiel zu erstellen.  
  
3.  Drücken Sie F5, um das Beispiel auszuführen.
