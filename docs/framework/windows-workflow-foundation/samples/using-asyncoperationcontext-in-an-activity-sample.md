---
title: "Verwenden von AsyncOperationContext in einem Aktivit&#228;tsbeispiel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0888a0bd-d227-4c00-ad6a-b654a01740e8
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Verwenden von AsyncOperationContext in einem Aktivit&#228;tsbeispiel
In diesem Beispiel wird veranschaulicht, wie eine benutzerdefinierte <xref:System.Activities.CodeActivity> entwickelt wird, die mit <xref:System.Activities.AsyncOperationContext> Arbeitsvorgänge außerhalb des Workflows asynchron ausführt.  
  
## Beispieldetails  
 Die Beispielaktivität verwendet die <xref:System.IO.FileStream.BeginWrite>\-Methode und <xref:System.IO.FileStream.EndWrite>\-Methode für die <xref:System.IO.FileStream>\-Klasse, um Daten asynchron in eine Datei zu schreiben.Das hier gezeigte Muster kann zur Verwendung mit anderen asynchronen Methoden angepasst werden.Während der asynchrone Vorgang ausgeführt wird, können andere Aktivitäten im Workflow ausgeführt werden, aber der Workflow kann nicht persistent gespeichert werden.  
  
#### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappe "Async.sln".  
  
2.  Erstellen Sie die Projektmappe, und führen Sie sie aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie den Vorgang fortsetzen.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\Async`  
  
## Siehe auch