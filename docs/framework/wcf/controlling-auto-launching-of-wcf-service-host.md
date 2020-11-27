---
title: Steuern des automatischen Starts des WCF-Diensthosts
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: 2033e693003d0b50bcdada428e4a5f451b3ad67e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255077"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a>Steuern des automatischen Starts des WCF-Diensthosts

Sie können die Funktion zum automatischen Starten von Windows Communication Foundation (WCF)-Dienst Hosts (WcfSvcHost.exe) für ein WCF-Dienst Bibliotheksprojekt steuern, wenn Sie ein anderes Projekt in derselben Visual Studio-Projekt Mappe Debuggen, die mehrere Projekte enthält.  
  
 Klicken Sie hierzu in **Projektmappen-Explorer** mit der rechten Maustaste auf das WCF-Dienstprojekt, wählen Sie **Eigenschaften** aus, und klicken Sie auf die Registerkarte **WCF-Optionen** . Das Kontrollkästchen **WCF-Dienst Host beim Debuggen eines anderen Projekts in derselben Projekt Mappe starten** ist standardmäßig aktiviert. Sie können das Kontrollkästchen deaktivieren, sodass der WCF-Dienst Host für dieses bestimmte Projekt nicht gestartet wird, wenn ein anderes Projekt in derselben Projekt Mappe deentschlbelt wird.  
  
 Dieses Verhalten wirkt sich weder auf das F5-Debugging noch auf die Funktionen zum Hinzufügen von Dienstverweisen für dieses Projekt aus.  
  
 Diese Option steht für die folgenden Projekte zur Verfügung:  
  
- WCF-Dienst Bibliotheksprojekt.  
  
- Bibliotheksprojekt für sequenziellen Workflowdienst  
  
- Bibliotheksprojekt für Statuscomputerworkflowdienst  
  
- Bibliotheksprojekt für Syndication-Dienst  
  
## <a name="see-also"></a>Weitere Informationen

- [WCF-Diensthost (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
