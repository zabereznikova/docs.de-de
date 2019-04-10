---
title: Installieren von Message Queuing (MSMQ)
ms.date: 03/30/2017
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
ms.openlocfilehash: 64736f8f0a34a53658dd2838738a3d36b3891d2d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59305090"
---
# <a name="installing-message-queuing-msmq"></a>Installieren von Message Queuing (MSMQ)
Im Folgenden wird beschrieben, wie Sie Message Queuing 4.0 und Message Queuing 3.0 installieren.  
  
> [!NOTE]
>  Message Queuing 4.0 ist in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] und [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] nicht verfügbar.  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a>So installieren Sie Message Queuing 4.0 unter Windows Server 2008 oder Windows Server 2008 R2  
  
1. Klicken Sie im Server-Manager **Features**.  
  
2. Im rechten Bereich unter **Featureübersicht**, klicken Sie auf **Features hinzufügen**.  
  
3. Erweitern Sie im angezeigten Fenster **Message Queuing-**.  
  
4. Erweitern Sie **Message Queuing-Dienste**.  
  
5. Klicken Sie auf **Verzeichnisdienstintegration** (bei Computern mit einer Domäne verknüpft ist), und klicken Sie dann **HTTP-Unterstützung**.  
  
6. Klicken Sie auf **Weiter**, klicken Sie dann auf **installieren**.  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a>So installieren Sie Message Queuing 4.0 unter Windows 7 oder Windows Vista  
  
1. Open **Systemsteuerung**.  
  
2. Klicken Sie auf **Programme** und dann unter **Programme und Funktionen**, klicken Sie auf **Windows-Funktionen ein- oder ausschalten**.  
  
3. Erweitern Sie Microsoft Message Queue (MSMQ)-Server, erweitern Sie Microsoft Message Queue (MSMQ)-Serverkernkomponenten, und aktivieren Sie die Kontrollkästchen für die zu installierenden Message Queuing-Funktionen:  
  
    -   MSMQ-Active Directory-Domänendienstintegration (für Computer, die einer Domäne zugewiesen sind)  
  
    -   MSMQ-HTTP-Unterstützung  
  
4. Klicken Sie auf **OK**.  
  
5. Wenn Sie aufgefordert werden, den Computer neu starten, klicken Sie auf **OK** um die Installation abzuschließen.  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a>So installieren Sie Message Queuing 3.0 unter Windows XP und Windows Server 2003  
  
1. Open **Systemsteuerung**.  
  
2. Klicken Sie auf **Software** , und klicken Sie dann auf **Windows-Komponenten hinzufügen**.  
  
3. Wählen Sie Message Queuing, und klicken Sie auf **Details**.  
  
    > [!NOTE]
    >  Wenn Sie [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] ausführen, wählen Sie den Anwendungsserver für den Zugriff auf Message Queuing aus.  
  
4. Stellen Sie sicher, dass die Option MSMQ-HTTP-Unterstützung auf der Detailseite ausgewählt ist.  
  
5. Klicken Sie auf **OK** , beenden die Seite "Details", und klicken Sie dann auf **Weiter**. Schließen Sie die Installation ab.  
  
6. Wenn Sie aufgefordert werden, den Computer neu starten, klicken Sie auf **OK** um die Installation abzuschließen.  
  
## <a name="see-also"></a>Siehe auch

- [Setupanweisungen](../../../../docs/framework/wcf/samples/set-up-instructions.md)
