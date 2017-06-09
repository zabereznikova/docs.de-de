---
title: "Grundlegende Verwendung der Aktivit&#228;ten SendParameters und ReceiveParameters | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1b6b1681-3d41-403f-bfe2-3f600f24aa8c
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Grundlegende Verwendung der Aktivit&#228;ten SendParameters und ReceiveParameters
Anhand dieses Beispiels wird die Verwendung der <xref:System.ServiceModel.Activities.SendParametersContent>\-Aktivität und der <xref:System.ServiceModel.Activities.ReceiveParametersContent>\-Aktivität veranschaulicht.Der Dienst macht einen Vorgang verfügbar, der ein Zeichenfolgenargument verwendet, und gibt die Eingabe in einem Echo\-Vorgang an den Client zurück.Im Beispiel wird gezeigt, wie die Parameter für diese Messagingaktivitäten eingerichtet werden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\SendReceiveParameters`  
  
#### Verwenden dieses Beispiels  
  
1.  Laden Sie die Projektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], und erstellen Sie das Projekt.  
  
2.  Führen Sie zunächst die unter "\[Projektmappenbasisverzeichnis\]\\EchoWorkflowService\\bin\\debug" generierte EchoWorkflowService\-Anwendung aus.  
  
3.  Führen Sie als Nächstes die unter "\[Projektmappenbasisverzeichnis\]\\EchoWorkflowClient\\bin\\debug" generierte EchoWorkflowClient\-Anwendung aus.  
  
4.  Der Client ruft den Echo\-Vorgang für den Dienst auf und gibt die Ergebnisse aus.Drücken Sie nach dem Abschluss die EINGABETASTE, um den Client und dann den Dienst zu beenden.  
  
## Siehe auch