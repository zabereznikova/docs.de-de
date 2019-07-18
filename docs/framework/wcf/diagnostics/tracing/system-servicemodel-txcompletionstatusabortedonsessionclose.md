---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: 7b1f6a2f4a344b566c76d0095942b84a8a4e76f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991626"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a>System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
Die angegebene Transaktion wurde abgebrochen, weil sie nicht abgeschlossen war, als die Sitzung geschlossen wurde, und das TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute auf FALSE festgelegt wurde.  
  
## <a name="description"></a>Beschreibung  
 Wird nachverfolgt, wenn die aktuelle aktive Sitzung geschlossen und die Transaktion nicht abgeschlossen wurde und TransactionAutoCompleteOnSessionClose auf `false` festgelegt wurde.  
  
## <a name="troubleshooting"></a>Problembehandlung  
 Diese Ablaufverfolgung gibt einen potenziellen Anwendungsfehler an, der untersucht werden sollte.  
  
## <a name="see-also"></a>Siehe auch

- [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
