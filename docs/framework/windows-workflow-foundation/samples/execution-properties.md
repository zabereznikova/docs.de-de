---
title: Ausführungseigenschaften
ms.date: 03/30/2017
ms.assetid: 31c009db-397c-4653-87e2-32dc77fa4b13
ms.openlocfilehash: 201fe222de1cb2029696a1694ae97815db5f913d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="execution-properties"></a>Ausführungseigenschaften
Dieses Beispiel zeigt, wie in einer benutzerdefinierten Aktivität eine Ausführungseigenschaft definiert und verwendet wird. Mit der Ausführungseigenschaft in diesem Beispiel wird die Vordergrundfarbe der Konsole bestimmt. Anhand eines Beispielworkflows wird gezeigt, wie mit verschiedenen logischen Ausführungspfaden (Verzweigungen einer <xref:System.Activities.Statements.Parallel>-Aktivität) trotz der überlappenden Ausführung von Aktivitäten (verzweigungsübergreifende Ausführung der <xref:System.Activities.Statements.Parallel>-Aktivität) unterschiedliche Konsolenfarben beibehalten werden können.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappe "ExecutionProperties.sln".  
  
    > [!NOTE]
    >  Wenn Sie "ThreeColors.xaml" vor dem Erstellen der Projektmappe anzeigen, wird ein Fehler angezeigt, da die verwendeten benutzerdefinierten Aktivitäten zur gleichen Zeit erstellt werden müssen wie die Projektmappe.  
  
2.  Erstellen Sie die Projektmappe, und führen Sie sie aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ExecutionProperties`