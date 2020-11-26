---
title: 'Dienst: Nicht autorisierte Sicherheitsaufrufe pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 1eeade5a-ea62-4757-b1f9-1b1b1746abd1
ms.openlocfilehash: db9e333f740f19e4f82ea0f1306a11e6c21ba996
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236922"
---
# <a name="service-security-calls-not-authorized-per-second"></a>Dienst: Nicht autorisierte Sicherheitsaufrufe pro Sekunde

Zählername: Nicht autorisierte Sicherheitsaufrufe pro Sekunde  
  
## <a name="description"></a>BESCHREIBUNG  

 Anzahl der eingehenden Nachrichten in einer Sekunde, die von einem gültigen Benutzer stammen und ordnungsgemäß geschützt sind, wobei der Benutzer allerdings nicht für die Durchführung spezifischer Aufgaben autorisiert ist.  
  
 Dieser Indikator wird erhöht, wenn die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>-Methode `false` zurückgibt.  
  
 Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)
