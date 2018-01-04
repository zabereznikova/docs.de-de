---
title: System.ServiceModel.MessageProcessingPaused
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6f767165486ac2dc6ce4ee5b3e0825eceef0c249
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelmessageprocessingpaused"></a>System.ServiceModel.MessageProcessingPaused
System.ServiceModel.MessageProcessingPaused  
  
## <a name="description"></a>Beschreibung  
 Zwischen den Threads wurde umgeschaltet, während sie eine Nachricht verarbeitet haben.  
  
 Nachrichtenverarbeitung kann aus den folgenden Gründen angehalten werden:  
  
-   ConcurrencyMode ist einzeln oder wiedereintrittsfähig, und der Dienst verarbeitet eine andere Nachricht.  
  
-   Transaktion wird aktiviert, und der Dienst verarbeitet eine andere Transaktion.  
  
-   Der Synchronisierungskontext ist nicht aktuell.  
  
## <a name="see-also"></a>Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
