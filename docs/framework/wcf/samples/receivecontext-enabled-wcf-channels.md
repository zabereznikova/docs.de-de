---
title: "ReceiveContext-aktivierte WCF-Kan&#228;le | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d990d119-7321-4b8c-852b-10256f59f9b0
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# ReceiveContext-aktivierte WCF-Kan&#228;le
In diesem Beispiel wird die Nützlichkeit WCF\-Kanälen mit Aktivierung von <xref:System.ServiceModel.Channels.ReceiveContext> erläutert.  Im Beispiel wird ein Dienst für die Suche nach dem Produkt von zwei Zahlen mithilfe eines NetMSMQ\-Kanals implementiert.  
  
 Mit der <xref:System.ServiceModel.Channels.ReceiveContext>\-Klasse kann eine Anwendung entscheiden, ob auf die Meldung zugegriffen werden oder sie für die weitere Verarbeitung in der Warteschlange belassen werden soll, selbst nachdem der Inhalt der Meldung überprüft wurde.  In diesem Beispiel sendet ein Client zufällige ganze Zahlen an eine Transaktionswarteschlange.  Der `ProductCalculator`\-Dienst empfängt die Meldungen und überprüft den Meldungsinhalt, der aus ganzen Zahlen besteht, um zu bestimmen, ob das Produkt berechnet werden kann.  Wenn der Dienstvorgang das Produkt nicht berechnet, wird die Meldung zurück an die Warteschlange gesendet und kann erneut vom Dienst empfangen werden, der die Warteschlange überwacht.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.  Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren:  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.  Dieses Beispiel befindet sich im folgenden Verzeichnis:  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\ReceiveContextProductGenerator`  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Stellen Sie sicher, dass Microsoft Message Queuing \(MSMQ\) installiert ist.  
  
    1.  So installieren Sie MSMQ unter [!INCLUDE[lserver](../../../../includes/lserver-md.md)]  
  
        1.  Klicken Sie in **Server\-Manager** auf **Funktionen**.  
  
        2.  Klicken Sie im rechten Bereich unter **Featureübersicht** auf **Features hinzufügen**.  
  
        3.  Erweitern Sie im jetzt geöffneten Fenster **Message Queuing**.  
  
        4.  Erweitern Sie **Message Queuing\-Dienste**.  
  
        5.  Klicken Sie auf **Verzeichnisdienstintegration** \(bei Computern, die zu einer Domäne gehören\), und klicken Sie dann auf **HTTP\-Unterstützung**.  
  
        6.  Klicken Sie auf **Weiter**, und klicken Sie dann auf **Installieren**.  
  
    2.  So installieren Sie MSMQ unter [!INCLUDE[wv](../../../../includes/wv-md.md)]  
  
        1.  Öffnen Sie die **Systemsteuerung**.  
  
        2.  Klicken Sie auf **Programme** und dann unter **Programme und Funktionen** auf **Windows\-Funktionen ein\- oder ausschalten**.  
  
        3.  Erweitern Sie **Microsoft Message Queue \(MSMQ\)\-Server**, erweitern Sie **Microsoft Message Queue \(MSMQ\)\-Serverkernkomponenten**, und aktivieren Sie die Kontrollkästchen für die zu installierenden Message Queuing\-Funktionen:  
  
            -   Message Queuing Server  
  
            -   MSMQ\-Active Directory\-Domänendienstintegration \(bei Computern, die einer Domäne zugewiesen sind\)  
  
            -   MSMQ\-HTTP\-Unterstützung  
  
        4.  Klicken Sie auf **OK**.  
  
        5.  Wenn Sie aufgefordert werden, den Computer neu zu starten, klicken Sie auf **OK**, um die Installation abzuschließen.  
  
2.  Stellen Sie sicher, dass [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] auf dem Computer installiert ist.  
  
3.  Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die ReceiveContextProductGenerator.sln\-Projektmappendatei.  
  
4.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
5.  Drücken Sie STRG\+F5, um die Projektmappe auszuführen.