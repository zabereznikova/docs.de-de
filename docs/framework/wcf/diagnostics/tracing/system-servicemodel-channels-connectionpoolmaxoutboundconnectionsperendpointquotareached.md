---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: 3e4e1ff7ea8d8768c8d902dc09bd3b78646c2caf
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256325"
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a>Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure

Der WS-AT-Protokolldienst konnte sich nicht auf einer Transaktion mit dem bereitgestellten Koordinationskontext eintragen.  
  
## <a name="description"></a>BESCHREIBUNG  

 Wird nachverfolgt, wenn MSDTC sich nicht auf einer Transaktion für ein gegebenes 2pc-Protokoll eintragen konnte.  Dies kann geschehen, wenn die Transaktion nicht mehr existiert, die Eintragung nicht mehr erlaubt ist oder zu viele Eintragungen vorhanden sind.  
  
## <a name="troubleshooting"></a>Problembehandlung  

 Überprüfen Sie die Statuszeichenfolge innerhalb der Ablaufverfolgungsnachricht, um zu bestimmen, ob ein ausführbares Element vorhanden ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [Ablaufverfolgung](index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../index.md)
