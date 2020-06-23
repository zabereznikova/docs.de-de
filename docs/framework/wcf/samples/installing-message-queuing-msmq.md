---
title: Installieren von Message Queuing (MSMQ)
description: Erfahren Sie, wie Sie Message Queuing 4,0 und Message Queuing 3,0 als Teil eines einmaligen Einrichtungs Verfahrens für die Verwendung mit WFC-Beispielen installieren.
ms.date: 03/30/2017
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
ms.openlocfilehash: 0d0cb87b40b1cb11eb7692c2fa1e890ec815b13d
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244464"
---
# <a name="installing-message-queuing-msmq"></a>Installieren von Message Queuing (MSMQ)
Im Folgenden wird beschrieben, wie Sie Message Queuing 4.0 und Message Queuing 3.0 installieren.  
  
> [!NOTE]
> Message Queuing 4,0 ist in Windows XP und Windows Server 2003 nicht verfügbar.  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a>So installieren Sie Message Queuing 4.0 unter Windows Server 2008 oder Windows Server 2008 R2  
  
1. Klicken Sie in Server-Manager auf **Features**.  
  
2. Klicken Sie im rechten Bereich unter **featurezusammenfassung**auf **Features hinzufügen**.  
  
3. Erweitern Sie im resultierenden Fenster **Message Queuing**.  
  
4. Erweitern Sie **Message Queuing Dienste**.  
  
5. Klicken Sie auf **Verzeichnisdienst Integration** (bei Computern, die einer Domäne beigetreten sind), und klicken Sie dann auf **http**  
  
6. Klicken Sie auf **weiter**, und klicken Sie dann auf **Installieren**.  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a>So installieren Sie Message Queuing 4.0 unter Windows 7 oder Windows Vista  
  
1. Öffnen Sie die **Systemsteuerung**.  
  
2. Klicken Sie auf **Programme** , und klicken Sie dann unter **Programme und Funktionen** **auf Windows-Funktionen ein-oder ausschalten**.  
  
3. Erweitern Sie Microsoft Message Queue (MSMQ)-Server, erweitern Sie Microsoft Message Queue (MSMQ)-Serverkernkomponenten, und aktivieren Sie die Kontrollkästchen für die zu installierenden Message Queuing-Funktionen:  
  
    - MSMQ-Active Directory-Domänendienstintegration (für Computer, die einer Domäne zugewiesen sind)  
  
    - MSMQ-HTTP-Unterstützung  
  
4. Klicken Sie auf **OK**.  
  
5. Wenn Sie aufgefordert werden, den Computer neu zu starten, klicken Sie auf **OK** , um die Installation abzuschließen.  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a>So installieren Sie Message Queuing 3.0 unter Windows XP und Windows Server 2003  
  
1. Öffnen Sie die **Systemsteuerung**.  
  
2. Klicken Sie auf Software **Entfernen** und dann auf **Windows-Komponenten hinzufügen**.  
  
3. Wählen Sie Message Queuing und klicken Sie auf **Details**.  
  
    > [!NOTE]
    > Wenn Sie Windows Server 2003 ausführen, wählen Sie Anwendungs Server aus, um auf Message Queuing zuzugreifen.  
  
4. Stellen Sie sicher, dass die Option MSMQ-HTTP-Unterstützung auf der Detailseite ausgewählt ist.  
  
5. Klicken Sie auf **OK** , um die Detailseite zu schließen, und klicken Sie dann auf **weiter**. Schließen Sie die Installation ab.  
  
6. Wenn Sie aufgefordert werden, den Computer neu zu starten, klicken Sie auf **OK** , um die Installation abzuschließen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Setupanweisungen](set-up-instructions.md)
