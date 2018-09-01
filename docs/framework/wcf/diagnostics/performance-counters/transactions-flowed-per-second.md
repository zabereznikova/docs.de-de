---
title: Übergegangene Transaktionen pro Sekunde
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: e77aef4cfff1e64f112e720183675dfb7aa25d27
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43392935"
---
# <a name="transactions-flowed-per-second"></a>Übergegangene Transaktionen pro Sekunde
Indikatorname: Transaktionen Flowed Per Second  
  
## <a name="description"></a>Beschreibung  
 Die Anzahl der in einer Sekunde an diesen Vorgang übergegangenen Transaktionen. Dieser Indikator wird jeweils inkrementiert, wenn eine TransaktionsID in einer Nachricht enthalten ist, die an den Vorgang gesendet wird.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)
