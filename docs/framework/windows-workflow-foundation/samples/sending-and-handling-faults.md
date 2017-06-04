---
title: "Senden und Behandeln von Fehlern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 98e8e04d-2ac9-4a33-ae08-462f757a7a14
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Senden und Behandeln von Fehlern
In diesem Beispiel wird veranschaulicht, wie die <xref:System.ServiceModel.Activities.SendReply>\-Messagingaktivität und <xref:System.ServiceModel.Activities.ReceiveReply>\-Messagingaktivität verwendet werden, um erwartete und unerwartete Fehler zu senden und zu empfangen.In diesem Szenario führt die erste Clientanforderung zu einem erwarteten Fehler, der in der <xref:System.ServiceModel.Activities.Send.KnownTypes%2A>\-Auflistung enthalten ist.Die nächsten Clientanforderungen führen zu unerwarteten Fehlern, bevor die abschließende Anforderung erfolgreich ist.  
  
## So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] mit erweiterten Berechtigungen, indem Sie mit der rechten Maustaste auf das Symbol [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] klicken und **Als Administrator ausführen** wählen.  
  
2.  Öffnen Sie die Faults.sln\-Projektmappendatei.  
  
3.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
4.  Führen Sie das Dienstprojekt aus.  
  
    1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das `FaultService`\-Projekt, und wählen Sie **Als Startprojekt festlegen** aus.  
  
    2.  Drücken Sie STRG\+F5.  
  
5.  Öffnen Sie eine weitere Kopie von [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] mit erweiterten Berechtigungen, indem Sie mit der rechten Maustaste auf das Symbol [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] klicken und **Als Administrator ausführen** wählen.  
  
6.  Öffnen Sie die Faults.sln\-Projektmappendatei.  
  
7.  Führen Sie das Clientprojekt aus.  
  
    1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das `FaultClient`\-Projekt, und wählen Sie **Als Startprojekt festlegen** aus.  
  
    2.  Drücken Sie STRG\+F5.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Faults`  
  
## Siehe auch