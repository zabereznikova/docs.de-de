---
title: Steuern des automatischen Starts des WCF-Diensthosts
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 65daceac9b865f3e8224c709d672344606905d9f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a>Steuern des automatischen Starts des WCF-Diensthosts
Sie haben die Möglichkeit zum Steuern der Autostartfunktion des [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Diensthosts (WcfSvcHost.exe) für ein [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst-Bibliotheksprojekt beim Debuggen eines anderen Projekts in der gleichen [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]-Projektmappe (bei Projektmappen mit mehreren Projekten).  
  
 Dazu, mit der Maustaste die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Dienstprojekt in **Projektmappen-Explorer**, wählen Sie **Eigenschaften**, und klicken Sie auf **WCF Optionen** Registerkarte. Die **starten WCF-Diensthost beim Debuggen eines anderen Projekts in derselben Projektmappe** Kontrollkästchen ist standardmäßig aktiviert. Deaktivieren Sie dieses Kontrollkästchen, wenn der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensthost für dieses bestimmte Projekt beim Debuggen eines anderen Projekts in der gleichen Projektmappe nicht gestartet werden soll.  
  
 Dieses Verhalten wirkt sich weder auf das F5-Debugging noch auf die Funktionen zum Hinzufügen von Dienstverweisen für dieses Projekt aus.  
  
 Diese Option steht für die folgenden Projekte zur Verfügung:  
  
-   Bibliotheksprojekt für [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst  
  
-   Bibliotheksprojekt für sequenziellen Workflowdienst  
  
-   Bibliotheksprojekt für Statuscomputerworkflowdienst  
  
-   Bibliotheksprojekt für Syndication-Dienst  
  
## <a name="see-also"></a>Siehe auch  
 [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
