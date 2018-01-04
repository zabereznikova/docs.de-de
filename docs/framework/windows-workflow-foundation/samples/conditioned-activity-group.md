---
title: "Bedingte Aktivitätsgruppe"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f76ef924-34ce-48ae-8c8d-48faf9697754
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7049f0ab787264893f334b8fe6aa0036e240a73f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="conditioned-activity-group"></a>Bedingte Aktivitätsgruppe
Im Beispiel wird eine Reisebuchungsanwendung veranschaulicht. Die <xref:System.Workflow.Activities.ConditionedActivityGroup> (CAG) verfügt über zwei Codeaktivitäten: Eine Car-Aktivität und eine Airline-Aktivität. Im `SimpleCAGWorkflow`-Konstruktor wird ein "travelNeedType"-ArrayList-Objekt mit den erforderlichen Reisebuchungstypen ausgefüllt. Sie ändern das CAG-Verhalten entsprechend, indem Sie eine oder beide `travelNeeds.Add`-Anweisungen auskommentieren. Die <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>-Bedingung sowohl der Car-Aktivität als auch der Airline-Aktivität werden mit der <xref:System.Workflow.Activities.CodeCondition> ausgefüllt. Die Car-Aktivität wird nur dann ausgeführt, wenn die `travelNeeds`-Auflistung über einen `TravelNeeds.Car`-Eintrag verfügt, und die Airline-Aktivität wird nur dann ausgeführt, wenn die `travelNeeds`-Auflistung über einen `TravelNeeds.Airline`-Eintrag verfügt.  
  
 Durch die Ausführung der einzelnen Aktivitäten wird der entsprechende Eintrag aus der Auflistung entfernt. Die <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A>-Standardbedingung gibt an, dass die CAG beendet werden soll, wenn keine untergeordneten Elemente ausgeführt werden oder bereit für die Ausführung sind (basierend auf deren <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>-Bedingungen). In diesem Beispiel bedeutet dies, dass die CAG beendet wird, wenn die `travelNeeds`-Auflistung leer ist.  
  
### <a name="to-build-the-sample"></a>So erstellen Sie das Beispiel  
  
1.  Öffnen Sie die Projektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Erstellen Sie die Projektmappe, indem Sie STRG+UMSCHALT+B drücken.  
  
3.  Führen Sie die Projektmappe ohne Debuggen aus, indem Sie STRG+F5 drücken.  
  
### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus  
  
-   Führen Sie im Eingabeaufforderungsfenster des SDKs die EXE-Datei im Ordner "SimpleCAG\bin\debug" aus (bzw. im Ordner "SimpleCAG\bin" für die Visual Basic-Version des Beispiels), der sich unter dem Hauptordner des Beispiels befindet.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren:  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\SimpleCAG`  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Workflow.Activities.ConditionedActivityGroup>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>  
 <xref:System.Workflow.Activities.CodeCondition>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A>
