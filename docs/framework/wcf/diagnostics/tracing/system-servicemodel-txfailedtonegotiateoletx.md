---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.date: 03/30/2017
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
ms.openlocfilehash: 7b468a57409e9a473a5bbf8e3324435e65e8c60b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295313"
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a>System.ServiceModel.TxFailedToNegotiateOleTx

Die OleTransactions-Protokollverhandlung wurde nicht für den angegebenen Koordinationskontext abgeschlossen.  
  
## <a name="description"></a>BESCHREIBUNG  

 Verfolgt nach, wann eine eingehende Transaktion mit OleTx-Informationen die angehängten OleTx-Informationen nicht verwenden kann und stattdessen wieder zur Nutzung des WS-AT zurückkehrt.  
  
## <a name="troubleshooting"></a>Problembehandlung  

 Gibt ein potenzielles Problem mit MSDTC RPC-Kommunikation zwischen den Computern an. Wenn viele dieser Ablaufverfolgungen im Protokoll angezeigt werden, kann sich eine drastische Abnahme der Leistung ergeben.  Wenn OleTx nicht gewünscht wird, legen Sie `OleTxUpgradeEnabled` in der WS-AT-Registrierungskonfiguration auf 0 (null) fest.  
  
## <a name="see-also"></a>Weitere Informationen

- [Ablaufverfolgung](index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../index.md)
