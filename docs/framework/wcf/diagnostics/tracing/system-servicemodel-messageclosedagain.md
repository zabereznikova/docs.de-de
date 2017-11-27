---
title: System.ServiceModel.MessageClosedAgain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7f3963fe28ccaf55b3946254e395b770619c8f22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelmessageclosedagain"></a>System.ServiceModel.MessageClosedAgain
System.ServiceModel.MessageClosedAgain  
  
## <a name="description"></a>Beschreibung  
 Eine Nachricht wurde wieder geschlossen.  
  
 Eine Nachricht sollte nur einmal geschlossen werden. Wird diese Ablaufverfolgung in Benutzererweiterungscode ausgegeben, weist dies darauf hin, dass der Benutzererweiterungscode im Begriff ist, eine Nachricht zu schließen, die bereits geschlossen wurde. Wird diese Ablaufverfolgung in Produktcode ausgegeben, weist dies darauf hin, dass der Benutzererweiterungscode eine Nachricht möglicherweise zu früh schließt.  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Verwenden der Ablaufverfolgung beheben](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
