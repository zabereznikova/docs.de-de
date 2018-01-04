---
title: "Grundlegende Aktivitätserstellung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c283a1a7-1245-4ecd-8072-206c1b4ca379
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 047948552471b33af8690b526db7c416e87f897a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="basic-activity-composition"></a>Grundlegende Aktivitätserstellung
In diesem Beispiel wird veranschaulicht, wie benutzerdefinierte Aktivitäten und vom System bereitgestellte Aktivitäten so zusammengesetzt werden, dass weitere benutzerdefinierte Aktivitäten entstehen.  
  
 Der Workflow, der die Survey-Aktivität verwendet, plant die Umfrage mit einer Liste von Fragen, und gibt dann die erhaltenen Antworten aus.  
  
## <a name="sample-details"></a>Beispieldetails  
 Das Beispiel verwendet drei benutzerdefinierte Aktivitäten. `ReadLine`Zeigt eine einfache <xref:System.Activities.NativeActivity> \<Zeichenfolge > erstellt eine <xref:System.Activities.Bookmark> nach Zeitplan und dann legt die `Return` <xref:System.Activities.OutArgument%601> auf den Wert mit dem der <xref:System.Activities.Bookmark> fortgesetzt wird. `Prompt`ist ein <xref:System.Activities.Activity%601> \<Zeichenfolge >, akzeptiert eine <xref:System.Activities.InArgument%601>< Zeichenfolge\> mit dem Namen `Text` und den Benutzer zurückgegeben, die Antwort in den `Result` <xref:System.Activities.OutArgument%601> \<Zeichenfolge >. Die `Prompt`-Aktivität verwendet die <xref:System.Activities.Statements.Sequence>-Aktivität und die <xref:System.Activities.Statements.WriteLine>-Aktivität, die im Lieferumfang von .NET Framework enthalten sind, von .NET Framework, und integriert auch die benutzerdefinierte `ReadLine`-Aktivität zum Abrufen von Benutzereingaben. Die letzte benutzerdefinierte Aktivität ist die `Survey`-Aktivität. Es ist ein <xref:System.Activities.Activity>< ICollection\<Zeichenfolge >>.  Diese Aktivität akzeptiert eine <xref:System.Activities.InArgument%601>< IEnumerable < Zeichenfolge\>> mit dem Namen `Questions` und füllt die `Result` out-Argument mit den Antworten. Die `Survey`-Aktivität verwendet <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Sequence> und <xref:System.Activities.Statements.AddToCollection%601> von .NET Framework und verwendet die `Prompt`-Aktivität, um die Fragen der Umfrage zu stellen und die Antworten abzurufen.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Öffnen der **BasicActivityComposition.sln** -Beispielprojektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Erstellen Sie die Projektmappe, und führen Sie sie aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\ActivityComposition`