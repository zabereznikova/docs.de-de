---
title: "Verf&#252;gbarmachen und Aufrufen von ActivityActions | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 97ce4797-426e-463d-9cc4-1261afad6df4
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Verf&#252;gbarmachen und Aufrufen von ActivityActions
In diesem Beispiel wird veranschaulicht, wie eine benutzerdefinierte Aktivität, die über eine <xref:System.Activities.ActivityAction> verfügt, entwickelt wird.Darüber hinaus wird die Verwendung dieser Aktivität veranschaulicht, indem eine Implementierung der <xref:System.Activities.ActivityAction> bereitgestellt wird.  
  
 Eine <xref:System.Activities.ActivityAction> ermöglicht einem Aktivitätsautor, "Löcher" mit bestimmten Signaturen verfügbar zu machen, an denen der Aktivitätsbenutzer ein benutzerdefiniertes Verhalten einbinden kann.So verfügt zum Beispiel die <xref:System.Activities.Statements.ForEach>\-Aktivität \(die auf eine Auflistung von Elementen wirkt\) über eine <xref:System.Activities.ActivityAction>, die es dem Aktivitätsbenutzer ermöglicht, Verhalten einzubinden, das auf das aktuelle Iterationselement wirkt.  
  
#### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Öffnen Sie die **ActivityAction.sln**\-Beispielprojektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Erstellen Sie die Projektmappe, und führen Sie sie aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ActivityAction`  
  
## Siehe auch