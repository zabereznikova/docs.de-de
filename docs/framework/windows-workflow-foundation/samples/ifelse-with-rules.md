---
title: IfElse mit Regeln
ms.date: 03/30/2017
ms.assetid: c4ad9bb2-9037-413a-8b14-59ed7b927a9e
ms.openlocfilehash: 31906f04149a0ca7659201965ca565c7fa2af305
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500528"
---
# <a name="ifelse-with-rules"></a>IfElse mit Regeln
Dieses Beispiel veranschaulicht die Verwendung einer Regelbedingung mit einer <xref:System.Workflow.Activities.IfElseActivity>-Aktivität.  
  
 Das Beispiel übergibt einen `OrderValue`-Parameter vom Host. Der Wert des Parameters wird in einer Regelbedingung für die erste Verzweigung der <xref:System.Workflow.Activities.IfElseActivity>-Aktivität verwendet. Wenn der Wert kleiner als 10.000 ist, wird die erste Verzweigung ausgeführt, und die <xref:System.Workflow.Activities.CodeActivity> -Aktivität in der ersten Verzweigung gibt **Get Manager Approval** an die Konsole. Wenn der Wert größer als 10.000 ist, ist die <xref:System.Workflow.Activities.CodeActivity> Aktivität in der zweiten Verzweigung ausgeführt wird, und gibt **Get VP Approval**.  
  
### <a name="to-build-the-sample"></a>So erstellen Sie das Beispiel  
  
1.  Öffnen Sie die Projektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Erstellen Sie die Projektmappe, indem Sie STRG+UMSCHALT+B drücken.  
  
3.  Führen Sie die Projektmappe ohne Debuggen aus, indem Sie STRG+F5 drücken.  
  
### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus  
  
-   Führen Sie im Eingabeaufforderungsfenster des SDKs die EXE-Datei im Ordner "IfElseWithRules\bin\debug" aus (bzw. im Ordner "IfElseWithRules\bin" für die Visual Basic-Version des Beispiels), der sich unter dem Hauptordner des Beispiels befindet.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren:  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\IfElseWithRules`  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Workflow.Activities.Rules>  
 <xref:System.Workflow.Activities.IfElseActivity>  
 <xref:System.Workflow.Activities.CodeActivity>  
 <xref:System.Workflow.Activities.Rules.RuleDefinitions>
