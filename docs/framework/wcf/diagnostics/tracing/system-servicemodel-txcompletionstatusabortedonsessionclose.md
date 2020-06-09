---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: c398fc52d5924c033500b95924f9287b43cc9e9d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84576602"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a>System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
Die angegebene Transaktion wurde abgebrochen, weil sie nicht abgeschlossen war, als die Sitzung geschlossen wurde, und das TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute auf FALSE festgelegt wurde.  
  
## <a name="description"></a>BESCHREIBUNG  
 Wird nachverfolgt, wenn die aktuelle aktive Sitzung geschlossen und die Transaktion nicht abgeschlossen wurde und TransactionAutoCompleteOnSessionClose auf `false` festgelegt wurde.  
  
## <a name="troubleshooting"></a>Problembehandlung  
 Diese Ablaufverfolgung gibt einen potenziellen Anwendungsfehler an, der untersucht werden sollte.  
  
## <a name="see-also"></a>Weitere Informationen

- [Ablaufverfolgung](index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../index.md)
