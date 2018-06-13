---
title: Übergegangene Transaktionen pro Sekunde
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: a71095b9fdd16d7e220be8a0aeb0a746bb50527e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33472917"
---
# <a name="transactions-flowed-per-second"></a>Übergegangene Transaktionen pro Sekunde
Indikatorname: Transaktionen Flowed Per Second  
  
## <a name="description"></a>Beschreibung  
 Die Anzahl der in einer Sekunde an diesen Vorgang übergegangenen Transaktionen. Dieser Indikator wird jeweils inkrementiert, wenn eine TransaktionsID in einer Nachricht enthalten ist, die an den Vorgang gesendet wird.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)
