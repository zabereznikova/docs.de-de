---
title: "Validierung von Aktivitätsbeziehungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f11a34e-ed67-4bce-88ce-7e96bbb4d052
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 03ac8e41f8126c6b05eac82d143291a0de491969
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="activity-relationships-validation"></a>Validierung von Aktivitätsbeziehungen
Dieses Beispiel besteht aus drei Aktivitäten: `CreateCity`, `CreateState` und `CreateCountry`. `CreateCity` muss sich innerhalb einer `CreateState`-Aktivität befinden, und `CreateState` muss sich innerhalb einer `CreateCountry`-Aktivität befinden. Für dieses Beispiel ist die Validierungslogik in Code für die `CreateState`-Aktivität und in XAML für die `CreateCity`-Aktivität. Beide Einschränkungen weisen das gleiche Verhalten auf.  
  
 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] stellt die folgenden drei Hilfsaktivitäten bereit, mit denen die Entwickler Beziehungen zwischen Aktivitäten überprüfen können:  
  
 <xref:System.Activities.Validation.GetParentChain>  
 Stellt die Auflistung aller Aktivitäten bereit, die zum übergeordneten Element des aktuellen Knotens gehören  
  
 <xref:System.Activities.Validation.GetChildSubtree>  
 Stellt die Auflistung aller Aktivitäten bereit, die zur Teilstruktur des aktuellen Knotens gehören, ohne den aktuellen Knoten  
  
 <xref:System.Activities.Validation.GetWorkflowTree>  
 Stellt die Auflistung aller Aktivitäten in derselben Struktur wie der aktuelle Knoten bereit  
  
 Im Beispiel wird eine <xref:System.Activities.Statements.ForEach%601>-Aktivität verwendet, um die Auflistung zu durchlaufen, die von <xref:System.Activities.Validation.GetParentChain> zurückgegeben wurde. Für jedes Element in der Auflistung wird der Typ mit `CreateCountry` verglichen (oder mit `CreateState`, wenn `CreateCity` überprüft wird). Wenn eine Übereinstimmung gefunden wird, wird das Ergebniskennzeichen auf `true` festgelegt. Schließlich wird <xref:System.Activities.Validation.AssertValidation> verwendet, um einen Validierungsfehler zu generieren, wenn das Ergebniskennzeichen auf `false` festgelegt wird.  
  
### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Beispielprojektmappe "ContainmentValidation.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Erstellen Sie die Projektmappe.  
  
3.  Drücken Sie STRG+F5, um das Programm zu starten.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren:  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ActivityRelationships`  
  
## <a name="see-also"></a>Siehe auch
