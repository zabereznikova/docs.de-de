---
title: "Installieren von Message Queuing (MSMQ) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Installieren von Message Queuing (MSMQ)
Im Folgenden wird beschrieben, wie Sie Message Queuing 4.0 und Message Queuing 3.0 installieren.  
  
> [!NOTE]
>  Message Queuing 4.0 ist in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] und [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] nicht verfügbar.  
  
#### So installieren Sie Message Queuing 4.0 unter Windows Server 2008 oder Windows Server 2008 R2  
  
1.  Klicken Sie in Server\-Manager auf **Features**.  
  
2.  Klicken Sie im rechten Bereich unter **Featureübersicht** auf **Features hinzufügen**.  
  
3.  Erweitern Sie im jetzt geöffneten Fenster **Message Queuing**.  
  
4.  Erweitern Sie **Message Queuing\-Dienste**.  
  
5.  Klicken Sie auf **Verzeichnisdienstintegration** \(bei Computern, die zu einer Domäne gehören\), und klicken Sie dann auf **HTTP\-Unterstützung**.  
  
6.  Klicken Sie auf **Weiter**, und klicken Siedann auf **Installieren**.  
  
#### So installieren Sie Message Queuing 4.0 unter Windows 7 oder Windows Vista  
  
1.  Öffnen Sie die **Systemsteuerung**.  
  
2.  Klicken Sie auf **Programme** und dann unter **Programme und Funktionen** auf **Windows\-Funktionen ein\- oder ausschalten**.  
  
3.  Erweitern Sie Microsoft Message Queue \(MSMQ\)\-Server, erweitern Sie Microsoft Message Queue \(MSMQ\)\-Serverkernkomponenten, und aktivieren Sie die Kontrollkästchen für die zu installierenden Message Queuing\-Funktionen:  
  
    -   MSMQ\-Active Directory\-Domänendienstintegration \(für Computer, die einer Domäne zugewiesen sind\)  
  
    -   MSMQ\-HTTP\-Unterstützung  
  
4.  Klicken Sie auf **OK**.  
  
5.  Wenn Sie aufgefordert werden, den Computer neu zu starten, klicken Sie auf **OK**, um die Installation abzuschließen.  
  
#### So installieren Sie Message Queuing 3.0 unter Windows XP und Windows Server 2003  
  
1.  Öffnen Sie die **Systemsteuerung**.  
  
2.  Klicken Sie auf **Software** und dann auf **Windows\-Komponenten hinzufügen\/entfernen**.  
  
3.  Wählen Sie Message Queuing aus, und klicken Sie auf **Details**.  
  
    > [!NOTE]
    >  Wenn Sie [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] ausführen, wählen Sie den Anwendungsserver für den Zugriff auf Message Queuing aus.  
  
4.  Stellen Sie sicher, dass die Option MSMQ\-HTTP\-Unterstützung auf der Detailseite ausgewählt ist.  
  
5.  Klicken Sie auf **OK**, um die Seite mit den Detailinformationen zu schließen, und klicken Sie dann auf **Weiter**.Schließen Sie die Installation ab.  
  
6.  Wenn Sie aufgefordert werden, den Computer neu zu starten, klicken Sie auf **OK**, um die Installation abzuschließen.  
  
## Siehe auch  
 [Setupanweisungen](../../../../docs/framework/wcf/samples/set-up-instructions.md)