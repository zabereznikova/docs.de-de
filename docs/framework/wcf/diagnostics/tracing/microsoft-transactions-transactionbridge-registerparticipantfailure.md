---
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.date: 03/30/2017
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
ms.openlocfilehash: e56a9ed1d837af27d481282e0e106d537ec41ee3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61997749"
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a>Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
Der WS-AT-Protokolldienst konnte keinen Teilnehmer für ein Steuerprotokoll registrieren.  
  
## <a name="description"></a>Beschreibung  
 Wird nachverfolgt, wenn MSDTC eine ungültige Registrierungsanforderung erkennt. Dies kann durch mehrere Abschlussregistrierungsanforderungen und interne Fehler verursacht werden.  
  
## <a name="troubleshooting"></a>Problembehandlung  
 Versuchen Sie nicht, mehr als einmal einen Abschluss zu registrieren.  Überprüfen Sie darüber hinaus die Statuszeichenfolge innerhalb der Ablaufverfolgungsnachricht, um zu bestimmen, ob irgendein ausführbares Element vorhanden ist.  
  
## <a name="see-also"></a>Siehe auch

- [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
