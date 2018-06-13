---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.date: 03/30/2017
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
ms.openlocfilehash: 7f376244343a75c16d5d2355642d626f666e42bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33483830"
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a>System.ServiceModel.TxFailedToNegotiateOleTx
Die OleTransactions-Protokollverhandlung wurde nicht für den angegebenen Koordinationskontext abgeschlossen.  
  
## <a name="description"></a>Beschreibung  
 Verfolgt nach, wann eine eingehende Transaktion mit OleTx-Informationen die angehängten OleTx-Informationen nicht verwenden kann und stattdessen wieder zur Nutzung des WS-AT zurückkehrt.  
  
## <a name="troubleshooting"></a>Problembehandlung  
 Gibt ein potenzielles Problem mit MSDTC RPC-Kommunikation zwischen den Computern an. Wenn viele dieser Ablaufverfolgungen im Protokoll angezeigt werden, kann sich eine drastische Abnahme der Leistung ergeben.  Wenn OleTx nicht gewünscht wird, legen Sie `OleTxUpgradeEnabled` in der WS-AT-Registrierungskonfiguration auf 0 (null) fest.  
  
## <a name="see-also"></a>Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
