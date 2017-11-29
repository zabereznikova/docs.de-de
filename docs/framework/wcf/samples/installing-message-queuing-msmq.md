---
title: Installieren von Message Queuing (MSMQ)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 89d81a25da6494fc9cbf041ae68f2985b5c90a81
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="installing-message-queuing-msmq"></a>Installieren von Message Queuing (MSMQ)
Im Folgenden wird beschrieben, wie Sie Message Queuing 4.0 und Message Queuing 3.0 installieren.  
  
> [!NOTE]
>  Message Queuing 4.0 ist in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] und [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] nicht verfügbar.  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a>So installieren Sie Message Queuing 4.0 unter Windows Server 2008 oder Windows Server 2008 R2  
  
1.  Klicken Sie im Server-Manager auf **Funktionen**.  
  
2.  Im rechten Bereich unter **Featureübersicht**, klicken Sie auf **Features hinzufügen**.  
  
3.  Erweitern Sie im jetzt geöffneten Fenster **Message Queuing**.  
  
4.  Erweitern Sie **Message Queuing-Dienste**.  
  
5.  Klicken Sie auf **Verzeichnisdienstintegration** (für Computer Mitglied einer Domäne), und klicken Sie auf **HTTP-Unterstützung**.  
  
6.  Klicken Sie auf **Weiter**, klicken Sie dann auf **installieren**.  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a>So installieren Sie Message Queuing 4.0 unter Windows 7 oder Windows Vista  
  
1.  Open **in der Systemsteuerung**.  
  
2.  Klicken Sie auf **Programme** und dann unter **Programme und Funktionen**, klicken Sie auf **Windows-Funktionen ein- oder ausschalten**.  
  
3.  Erweitern Sie Microsoft Message Queue (MSMQ)-Server, erweitern Sie Microsoft Message Queue (MSMQ)-Serverkernkomponenten, und aktivieren Sie die Kontrollkästchen für die zu installierenden Message Queuing-Funktionen:  
  
    -   MSMQ-Active Directory-Domänendienstintegration (für Computer, die einer Domäne zugewiesen sind)  
  
    -   MSMQ-HTTP-Unterstützung  
  
4.  Klicken Sie auf **OK**.  
  
5.  Wenn Sie aufgefordert werden, den Computer neu starten, klicken Sie auf **OK** um die Installation abzuschließen.  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a>So installieren Sie Message Queuing 3.0 unter Windows XP und Windows Server 2003  
  
1.  Open **in der Systemsteuerung**.  
  
2.  Klicken Sie auf **Software** , und klicken Sie dann auf **Windows-Komponenten hinzufügen**.  
  
3.  Wählen Sie Message Queuing, und klicken Sie auf **Details**.  
  
    > [!NOTE]
    >  Wenn Sie [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] ausführen, wählen Sie den Anwendungsserver für den Zugriff auf Message Queuing aus.  
  
4.  Stellen Sie sicher, dass die Option MSMQ-HTTP-Unterstützung auf der Detailseite ausgewählt ist.  
  
5.  Klicken Sie auf **OK** , schließen die Seite "Details", und klicken Sie dann auf **Weiter**. Schließen Sie die Installation ab.  
  
6.  Wenn Sie aufgefordert werden, den Computer neu starten, klicken Sie auf **OK** um die Installation abzuschließen.  
  
## <a name="see-also"></a>Siehe auch  
 [Setupanweisungen](../../../../docs/framework/wcf/samples/set-up-instructions.md)
