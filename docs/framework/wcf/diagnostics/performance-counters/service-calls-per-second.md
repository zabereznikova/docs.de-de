---
title: 'Dienst: Aufrufe pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
ms.openlocfilehash: 5189a78e2655707d165f187e06ac9a60d055eac0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43499886"
---
# <a name="service-calls-per-second"></a>Dienst: Aufrufe pro Sekunde
Indikatorname: Calls Per Second.  
  
## <a name="description"></a>Beschreibung  
 Die Anzahl der Aufrufe an diesen Dienst pro Sekunde.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F). Dabei gibt der Zähler (N) die Anzahl der im letzten Messintervall durchgeführten Operationen und der Nenner (D) die Anzahl der Ticks im letzten Messintervall an. F ist die Tickfrequenz.
