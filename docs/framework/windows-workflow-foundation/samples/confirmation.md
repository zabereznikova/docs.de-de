---
title: "Bestätigung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8637aeaf-ac9e-49b8-93f4-da15dee45277
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 42d9fad968b471c63dbdac2145bb9e84afed183b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="confirmation"></a>Bestätigung
In diesem Beispiel werden vier allgemeine Szenarien im Zusammenhang mit der Verwendung von <xref:System.Activities.Statements.CompensableActivity> und der Bestätigung veranschaulicht. Im Beispiel werden vier Workflows ausgeführt, um die Bestätigung zu veranschaulichen. Dieses Beispiel ist in deklarativen und imperativen Versionen verfügbar.  
  
## <a name="confirm-a-compensable-activity"></a>Bestätigen einer kompensierbaren Aktivität  
 Der erste Workflow veranschaulicht, wie eine kompensierbare Aktivität bestätigt wird, und besteht aus einer Sequenz von zwei <xref:System.Activities.Statements.CompensableActivity>-Instanzen. Nach Abschluss der zweiten <xref:System.Activities.Statements.CompensableActivity> bestätigt eine Confirm-Aktivität die erste Aktivität. Wenn der Workflow erfolgreich abgeschlossen wird, werden alle <xref:System.Activities.Statements.CompensableActivity>-Instanzen, die nicht bestätigt oder kompensiert wurden, automatisch mit der Standardreihenfolge bestätigt. Ohne die Confirm-Aktivität wäre die zweite <xref:System.Activities.Statements.CompensableActivity> zuerst bestätigt worden.  
  
## <a name="explicit-compensation"></a>Explizite Kompensierung  
 Das zweite Szenario zeigt die Auswirkungen auf die Standardbestätigung, wenn eine <xref:System.Activities.Statements.CompensableActivity> explizit kompensiert wird. Der Workflow besteht aus einer Sequenz von zwei <xref:System.Activities.Statements.CompensableActivity>-Aktivitäten, nachdem die zweite abgeschlossen wurde, wird die erste explizit kompensiert. Wenn der Workflow abgeschlossen wird, wird als Ergebnis nur die zweite <xref:System.Activities.Statements.CompensableActivity> bestätigt.  
  
## <a name="controlling-the-order-of-confirmation-for-nested-compensableactivity-activities"></a>Steuern der Bestätigungsreihenfolge für geschachtelte CompensableActivity-Aktivitäten  
 Das dritte Szenario zeigt, wie die Bestätigungsreihenfolge für geschachtelte <xref:System.Activities.Statements.CompensableActivity> gesteuert wird. Das Szenario besteht aus einer <xref:System.Activities.Statements.CompensableActivity> als Stamm des Workflows. Der Text der <xref:System.Activities.Statements.CompensableActivity> als Stamm ist eine Sequenz von drei <xref:System.Activities.Statements.CompensableActivity>. Der <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> für die <xref:System.Activities.Statements.CompensableActivity> als Stamm ist eine Sequenz, die angibt, zuerst die erste und dann die zweite geschachtelte <xref:System.Activities.Statements.CompensableActivity> zu bestätigen. Wenn der Workflow abgeschlossen wird, wird <xref:System.Activities.Statements.CompensableActivity> als Stamm bestätigt, dann wird die erste, die zweite und die dritte geschachtelte <xref:System.Activities.Statements.CompensableActivity> bestätigt, in dieser Reihenfolge. Als Ergebnis wird die standardmäßige Bestätigungsreihenfolge im Grunde umgekehrt. Da die dritte <xref:System.Activities.Statements.CompensableActivity> nicht explizit als Teil von <xref:System.Activities.Statements.CompensableActivity> als Stamm von <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> bestätigt wurde, wird sie nach der Standardreihenfolge bestätigt. Da sie jedoch die einzige unbestätigte <xref:System.Activities.Statements.CompensableActivity> ist, bedeutet dies nur, dass sie bestätigt ist.  
  
## <a name="scoping-of-variables"></a>Bereiche von Variablen  
 Das vierte Szenario zeigt, wie die Lebensdauer von Variablen, die für eine <xref:System.Activities.Statements.CompensableActivity> oder eine der übergeordneten Aktivitäten definiert sind, noch im Gültigkeitsbereich liegt, wenn die Handler <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>, <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> oder <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> ausgeführt werden, auch wenn die Aktivität oder der Workflow abgeschlossen wurde. Der Workflow besteht aus einer Sequenz von zwei <xref:System.Activities.Statements.CompensableActivity>. Im Text der ersten wird die Variable `mySum` auf die Summe von 5 und 10 festgelegt, und das Ergebnis wird ausgegeben. Im Text der zweiten <xref:System.Activities.Statements.CompensableActivity> wird die Summe auf die Summe der vorhandenen Summe und 7 festgelegt, und das Ergebnis wird ausgegeben. Ein benutzerdefinierter Bestätigungshandler wird für die erste <xref:System.Activities.Statements.CompensableActivity> definiert, die die Summe ausgibt, 7 subtrahiert und die Summe wieder ausgibt. Durch Überprüfung der ausgegebenen Summen wird deutlich, dass die Variable nicht nur für die Texte der beiden <xref:System.Activities.Statements.CompensableActivity>, sondern auch für den <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> im Bereich liegt.  
  
#### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus  
  
1.  Laden Sie die Projektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Führen Sie die Anwendung "ConfirmationSample.exe" aus.  
  
3.  Achten Sie auf die folgende Ausgabe:  
  
 **Explizite Bestätigung: Anfang workflowCompensableActivity1: BodyCompensableActivity2: BodyCompensableActivity1: Bestätigung HandlerEnd von workflowCompensableActivity2: Bestätigung HandlerExplicit Kompensierung: Anfang workflowCompensableActivity1: BodyCompensableActivity2: BodyCompensableActivity1: Kompensierung HandlerEnd von workflowCompensableActivity2: Bestätigung HandlerCustom Bestätigung Handler: Anfang workflowCompensableActivity1: BodyCompensableActivity2: BodyCompensableActivity3: BodyEnd von workflowCompensableActivity1: Bestätigung HandlerCompensableActivity2: Bestätigung HandlerCompensableActivity3: Bestätigung HandlerVariable Zugriff in einem Ereignishandler Bestätigung: Anfang workflowCompensableActivity1: BodyCompensableActivity1: die Summe: 15CompensableActivity2: BodyCompensableActivity2: 7 hinzufügen, um die sumCompensableActivity2: die Summe ist jetzt: 22End von workflowCompensableActivity2: Bestätigung HandlerCompensableActivity1: Bestätigung HandlerCompensableActivity2: die Summe: 22CompensableActivity2: nach Abzug von 12 ist die Summe jetzt: 10Press EINGABETASTE zu beenden.**  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\Confirmation`