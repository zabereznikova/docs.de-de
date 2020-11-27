---
title: Übergegangene Transaktionen pro Sekunde
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: b47219bd58a9b6c4401baa73177928ddca5b6a8b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254141"
---
# <a name="transactions-flowed-per-second"></a>Übergegangene Transaktionen pro Sekunde

Indikatorname: Transactions Flowed Per Second  
  
## <a name="description"></a>BESCHREIBUNG  

 Die Anzahl der in einer Sekunde an diesen Vorgang übergegangenen Transaktionen. Dieser Indikator wird jeweils inkrementiert, wenn eine Transaktions-ID in einer Nachricht enthalten ist, die an den Vorgang gesendet wird.  
  
 Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)
