---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.date: 03/30/2017
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
ms.openlocfilehash: 2de1aa51d58d9d86f953e027fd3f7f172e3887d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917058"
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a>System.ServiceModel.TxFailedToNegotiateOleTx
Die OleTransactions-Protokollverhandlung wurde nicht für den angegebenen Koordinationskontext abgeschlossen.  
  
## <a name="description"></a>Beschreibung  
 Verfolgt nach, wann eine eingehende Transaktion mit OleTx-Informationen die angehängten OleTx-Informationen nicht verwenden kann und stattdessen wieder zur Nutzung des WS-AT zurückkehrt.  
  
## <a name="troubleshooting"></a>Problembehandlung  
 Gibt ein potenzielles Problem mit MSDTC RPC-Kommunikation zwischen den Computern an. Wenn viele dieser Ablaufverfolgungen im Protokoll angezeigt werden, kann sich eine drastische Abnahme der Leistung ergeben.  Wenn OleTx nicht gewünscht wird, legen Sie `OleTxUpgradeEnabled` in der WS-AT-Registrierungskonfiguration auf 0 (null) fest.  
  
## <a name="see-also"></a>Siehe auch

- [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
