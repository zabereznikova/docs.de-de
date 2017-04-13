---
title: "Korrelierter Rechner | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c365166e-6552-49a4-bf17-9f4e597d4d41
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Korrelierter Rechner
In diesem Beispiel wird veranschaulicht, wie die Messagingaktivitäten \(<xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply>\) im Designer auf Grundlage eines Parameters in der Meldung mit inhaltsbasierter Korrelation verwendet werden.In diesem Szenario befinden sich die Vorgänge des Rechners in einem parallelen Konvoi.Sowohl eine Instanz als auch eine Korrelation \(basierend auf `CalculatorId`\) werden erstellt, wenn die erste Meldung an den Workflow gesendet wird; nachfolgende Meldungen mit derselben `CalculatorId` werden an diese Instanz weitergeleitet, bis der Reset\-Vorgang aufgerufen wird.Der Client wird als WPF\-Anwendung implementiert, die einen codebasierten Clientproxy verwendet, um mit dem Dienst zu kommunizieren.  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Starten Sie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] mit erhöhten Rechten, und öffnen Sie die Projektmappendatei "For.sln".  
  
    1.  Navigieren Sie zu dem Ordner, der [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] enthält.  
  
    2.  Klicken Sie mit der rechten Maustaste auf "Devenv.exe", und wählen Sie **Als Administrator ausführen** aus.  
  
2.  Öffnen Sie die Projektmappendatei " CorrelatedCalculator.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
3.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
4.  Drücken Sie STRG\+F5, um das Dienstprojekt auszuführen.  
  
5.  Sobald der Dienst bereit ist und Nachrichten überwacht, klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf das Clientprojekt, und führen Sie es aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\CorellatedCalculator`  
  
## Siehe auch