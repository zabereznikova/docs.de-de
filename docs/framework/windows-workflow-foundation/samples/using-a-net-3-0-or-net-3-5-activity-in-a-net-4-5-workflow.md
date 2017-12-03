---
title: "Verwenden einer .NET Framework 3.0- oder .NET Framework 3.5-Aktivität in einem .NET Framework 4.5-Workflow"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c53fd4c-5dd0-4fb4-ab6b-111302629548
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 227c4e6ee566cd88982456d0045ab59221b26664
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="using-a-net-framework-30-or-net-framework-35-activity-in-a-net-framework-45-workflow"></a>Verwenden einer .NET Framework 3.0- oder .NET Framework 3.5-Aktivität in einem .NET Framework 4.5-Workflow
Die <xref:System.Activities.Statements.Interop>-Aktivität ermöglicht die Ausführung einer .NET Framework 3.0 [!INCLUDE[wf](../../../../includes/wf-md.md)]-Aktivität in einem [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]-Workflow. Dieses Beispiel veranschaulicht, wie die <xref:System.Activities.Statements.Interop>-Aktivität verwendet wird, um eine Zeichenfolge als Argument an eine benutzerdefinierte [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]-Aktivität zu übergeben.  
  
## <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die Projektmappendatei "SimpleInterop.sln".  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\SimpleInterop`  
  
## <a name="see-also"></a>Siehe auch
