---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 35f149423fc8c0cd2a25834742d7c8b79ad8d8c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a>System.ServiceModel.ManualFlowThrottleLimitReached
System.ServiceModel.ManualFlowThrottleLimitReached  
  
## <a name="description"></a>Beschreibung  
 Das System hat den für die ManualFlowControlLimit-Drosselung festgelegten Grenzwert erreicht. Der Drosselungswert kann geändert werden, indem die ManualFlowControlLimit-Eigenschaft nach Bedarf entweder auf ServiceHost oder InstanceContext festgelegt wird.  
  
 Diese Ablaufverfolgung wird ausgegeben, wenn die manuelle Flussteuerungsgrenze anfangs auf 0 (null) reduziert wird. Eine spätere Änderung auf 0 (null) wird nicht verfolgt. Eine Flusssteuerungsgrenze für den Instanzkontext wird einmal für jeden Kontext verfolgt.  
  
## <a name="see-also"></a>Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
