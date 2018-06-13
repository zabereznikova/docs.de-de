---
title: Steuern des automatischen Starts des WCF-Diensthosts
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: 63c3ca00c0cdc0b28de0fe245b616acd04ca50fe
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809887"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a>Steuern des automatischen Starts des WCF-Diensthosts
Beim Debuggen von einem anderen Projekt in der gleichen Visual Studio-Projektmappe, die mehrere Projekte enthält, können Sie die Autostartfunktion des Windows Communication Foundation (WCF)-Diensthost (WcfSvcHost.exe) für einen WCF-Dienstbibliotheksprojekt steuern.  
  
 Zu diesem Zweck Maustaste das WCF-Dienstprojekt in **Projektmappen-Explorer**, wählen Sie **Eigenschaften**, und klicken Sie auf **WCF Optionen** Registerkarte. Die **starten WCF-Diensthost beim Debuggen eines anderen Projekts in derselben Projektmappe** Kontrollkästchen ist standardmäßig aktiviert. Sie können das Kontrollkästchen deaktivieren, damit, dass WCF-Diensthost für dieses bestimmte Projekt nicht gestartet wird, wenn ein anderes Projekt in derselben Projektmappe gedebuggt wird.  
  
 Dieses Verhalten wirkt sich weder auf das F5-Debugging noch auf die Funktionen zum Hinzufügen von Dienstverweisen für dieses Projekt aus.  
  
 Diese Option steht für die folgenden Projekte zur Verfügung:  
  
-   Bibliotheksprojekt für WCF-Dienst.  
  
-   Bibliotheksprojekt für sequenziellen Workflowdienst  
  
-   Bibliotheksprojekt für Statuscomputerworkflowdienst  
  
-   Bibliotheksprojekt für Syndication-Dienst  
  
## <a name="see-also"></a>Siehe auch  
 [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
