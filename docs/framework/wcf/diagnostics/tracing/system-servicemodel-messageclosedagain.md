---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: a18355d55359df665d0e936ce95da34bf07aec6a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59181336"
---
# <a name="systemservicemodelmessageclosedagain"></a>System.ServiceModel.MessageClosedAgain
System.ServiceModel.MessageClosedAgain  
  
## <a name="description"></a>Beschreibung  
 Eine Nachricht wurde wieder geschlossen.  
  
 Eine Nachricht sollte nur einmal geschlossen werden. Wird diese Ablaufverfolgung in Benutzererweiterungscode ausgegeben, weist dies darauf hin, dass der Benutzererweiterungscode im Begriff ist, eine Nachricht zu schließen, die bereits geschlossen wurde. Wird diese Ablaufverfolgung in Produktcode ausgegeben, weist dies darauf hin, dass der Benutzererweiterungscode eine Nachricht möglicherweise zu früh schließt.  
  
## <a name="see-also"></a>Siehe auch

- [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
