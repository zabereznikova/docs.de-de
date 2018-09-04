---
title: Grundlegende Aktivitätserstellung
ms.date: 03/30/2017
ms.assetid: c283a1a7-1245-4ecd-8072-206c1b4ca379
ms.openlocfilehash: ade8187ca44a8182b55cf0f01e5bfe5a9a747255
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518375"
---
# <a name="basic-activity-composition"></a>Grundlegende Aktivitätserstellung
In diesem Beispiel wird veranschaulicht, wie benutzerdefinierte Aktivitäten und vom System bereitgestellte Aktivitäten so zusammengesetzt werden, dass weitere benutzerdefinierte Aktivitäten entstehen.  
  
 Der Workflow, der die Survey-Aktivität verwendet, plant die Umfrage mit einer Liste von Fragen, und gibt dann die erhaltenen Antworten aus.  
  
## <a name="sample-details"></a>Beispieldetails  
 Das Beispiel verwendet drei benutzerdefinierte Aktivitäten. `ReadLine` Zeigt eine einfache <xref:System.Activities.NativeActivity> \<Zeichenfolge > erstellt eine <xref:System.Activities.Bookmark> Wenn geplant ist, und dann legt die `Return` <xref:System.Activities.OutArgument%601> auf den Wert mit dem die <xref:System.Activities.Bookmark> fortgesetzt wird. `Prompt` ist ein <xref:System.Activities.Activity%601> \<Zeichenfolge >, akzeptiert eine <xref:System.Activities.InArgument%601>< Zeichenfolge\> mit dem Namen `Text` und der Benutzer Antwort zurückgegeben. die `Result` <xref:System.Activities.OutArgument%601> \<Zeichenfolge >. Die `Prompt`-Aktivität verwendet die <xref:System.Activities.Statements.Sequence>-Aktivität und die <xref:System.Activities.Statements.WriteLine>-Aktivität, die im Lieferumfang von .NET Framework enthalten sind, von .NET Framework, und integriert auch die benutzerdefinierte `ReadLine`-Aktivität zum Abrufen von Benutzereingaben. Die letzte benutzerdefinierte Aktivität ist die `Survey`-Aktivität. Es ist ein <xref:System.Activities.Activity>< ICollection\<Zeichenfolge >>.  Diese Aktivität akzeptiert eine <xref:System.Activities.InArgument%601>< IEnumerable < Zeichenfolge\>> mit dem Namen `Questions` und füllt die `Result` out-Argument mit den Antworten. Die `Survey`-Aktivität verwendet <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Sequence> und <xref:System.Activities.Statements.AddToCollection%601> von .NET Framework und verwendet die `Prompt`-Aktivität, um die Fragen der Umfrage zu stellen und die Antworten abzurufen.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Öffnen der **BasicActivityComposition.sln** -Beispielprojektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Erstellen Sie die Projektmappe, und führen Sie sie aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\ActivityComposition`