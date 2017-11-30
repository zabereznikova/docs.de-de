---
title: "Ausführungseigenschaften"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31c009db-397c-4653-87e2-32dc77fa4b13
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ab7c81f051e6e65509d232479fd9f4ebe00ac99d
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2017
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
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ExecutionProperties`