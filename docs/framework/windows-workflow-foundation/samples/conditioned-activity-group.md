---
title: Bedingte Aktivitätsgruppe
ms.date: 03/30/2017
ms.assetid: f76ef924-34ce-48ae-8c8d-48faf9697754
ms.openlocfilehash: 144a6c76ea6314c553e201fe4e2364890d869f34
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861204"
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
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\SimpleCAG`  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Workflow.Activities.ConditionedActivityGroup>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>  
 <xref:System.Workflow.Activities.CodeCondition>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A>
