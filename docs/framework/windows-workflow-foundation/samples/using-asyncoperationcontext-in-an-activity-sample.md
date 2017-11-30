---
title: "Verwenden von AsyncOperationContext in einem Aktivitätsbeispiel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0888a0bd-d227-4c00-ad6a-b654a01740e8
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ae62192517ee9117092ff11d2da5212d5a1c1fff
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2017
---
# <a name="using-asyncoperationcontext-in-an-activity-sample"></a>Verwenden von AsyncOperationContext in einem Aktivitätsbeispiel
In diesem Beispiel wird veranschaulicht, wie eine benutzerdefinierte <xref:System.Activities.CodeActivity> entwickelt wird, die <xref:System.Activities.AsyncCodeActivityContext> verwendet, um Arbeiten asynchron außerhalb des Workflows auszuführen.  
  
## <a name="sample-details"></a>Beispieldetails  
 Die Beispielaktivität verwendet die <xref:System.IO.FileStream.BeginWrite%2A>-Methode und <xref:System.IO.FileStream.EndWrite%2A>-Methode für die <xref:System.IO.FileStream>-Klasse, um Daten asynchron in eine Datei zu schreiben. Das hier gezeigte Muster kann zur Verwendung mit anderen asynchronen Methoden angepasst werden. Während der asynchrone Vorgang ausgeführt wird, können andere Aktivitäten im Workflow ausgeführt werden, aber der Workflow kann nicht persistent gespeichert werden.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappe "Async.sln".  
  
2.  Erstellen Sie die Projektmappe, und führen Sie sie aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\Async`