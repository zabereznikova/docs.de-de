---
title: Steuern des automatischen Starts des WCF-Diensthosts
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: f7f58a684449819fe945ad1ba5bff12f425c8294
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712391"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a>Steuern des automatischen Starts des WCF-Diensthosts
Sie können den automatischen Start-Funktion von Windows Communication Foundation (WCF)-Diensthost (WcfSvcHost.exe) für einen WCF-Dienstbibliotheksprojekt, steuern, beim Debuggen eines anderen Projekts in der gleichen Visual Studio-Projektmappe mit mehreren Projekten.  
  
 Dazu, mit der Maustaste in den WCF-Dienstprojekt **Projektmappen-Explorer**, wählen Sie **Eigenschaften**, und klicken Sie auf **WCF-Optionen** Registerkarte. Die **starten WCF-Diensthost beim Debuggen von einem anderen Projekt in der gleichen Projektmappe** Kontrollkästchen ist standardmäßig aktiviert. Sie können das Kontrollkästchen deaktivieren, so, dass WCF-Diensthost für dieses bestimmte Projekt beim Debuggen eines anderen Projekts in der gleichen Projektmappe nicht gestartet wird.  
  
 Dieses Verhalten wirkt sich weder auf das F5-Debugging noch auf die Funktionen zum Hinzufügen von Dienstverweisen für dieses Projekt aus.  
  
 Diese Option steht für die folgenden Projekte zur Verfügung:  
  
-   WCF-Dienstbibliotheksprojekt.  
  
-   Bibliotheksprojekt für sequenziellen Workflowdienst  
  
-   Bibliotheksprojekt für Statuscomputerworkflowdienst  
  
-   Bibliotheksprojekt für Syndication-Dienst  
  
## <a name="see-also"></a>Siehe auch
- [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
