---
title: Verwenden einer .NET Framework 3.0- oder .NET Framework 3.5-Aktivität in einem .NET Framework 4.5-Workflow
ms.date: 03/30/2017
ms.assetid: 6c53fd4c-5dd0-4fb4-ab6b-111302629548
ms.openlocfilehash: ab2e93918617bd1ca21fb32878d446db0dd2ef16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-a-net-framework-30-or-net-framework-35-activity-in-a-net-framework-45-workflow"></a>Verwenden einer .NET Framework 3.0- oder .NET Framework 3.5-Aktivität in einem .NET Framework 4.5-Workflow
Die <xref:System.Activities.Statements.Interop> Aktivität können Sie für die Ausführung einer .NET Framework 3.0 Windows Workflow Foundation (WF)-Aktivität innerhalb einer [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] Workflow. Dieses Beispiel veranschaulicht, wie die <xref:System.Activities.Statements.Interop>-Aktivität verwendet wird, um eine Zeichenfolge als Argument an eine benutzerdefinierte [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]-Aktivität zu übergeben.  
  
## <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die Projektmappendatei "SimpleInterop.sln".  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\SimpleInterop`  
  
## <a name="see-also"></a>Siehe auch
